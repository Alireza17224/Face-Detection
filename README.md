# Face-Detection Api

![ezgif-3-d8547e8dd2](https://user-images.githubusercontent.com/74126199/161736453-8cb2757f-7693-4bd8-a8f2-832c978b2d98.jpg)

Hi ! I am Alireza Mosavi a developer .

I would like to introduce my Face-Detection-Api can make login or sign-up faster and easier.

# Face-Detection Api packages

In this api I used Node.js for deploying.

Also i have used these libraries.

@tensorflow/tfjs-node": 3.12.0

@vladmandic/face-api": 1.6.1

body-parser:1.19.1

canvas: 2.8.0

express: 4.17.1

express-fileupload: 1.2.1

mkdirp: 1.0.4

node-json-db: 1.4.1

path: 0.12.7

uuid: 8.3.2

# Face-Detection Api Testing

For testing application first you need to clone it : 

```
git init
git clone https://github.com/Alireza17224/Face-Detection
```
After That these files will be downloaded for you.

![Picture1](https://user-images.githubusercontent.com/74126199/161724005-6e9a3263-7b28-4ded-8672-3024e34eb746.png)

after that find the folder that you cloned the files in it and then open admin powershell.

![Picture2](https://user-images.githubusercontent.com/74126199/161724774-5f5dc53f-ebbf-4c19-89fe-e5a1d6aa8d0b.png)

**You need to download npm before using this api**

Then Please type 
```
npm install
```
![Downloading](https://user-images.githubusercontent.com/74126199/161725369-6012acc3-f9de-4b48-a82c-5f0e37d7f553.png)

Then for running the js file type 
```
node app.js
```
Now the api is available in ``` http://localhost:3000 ```

![Picture4](https://user-images.githubusercontent.com/74126199/161725787-ed04bf86-b4f9-4f6b-af41-3e81ec6100fc.png)

You can send requests by Postman Application.

![postman](https://user-images.githubusercontent.com/74126199/161726757-37e5039d-3b4f-426d-ae0a-529d140782bf.png)

# Using this api in your projects

For using this api in your project you can do what you like or prefer.

But See this pictures first.

![Picture1](https://user-images.githubusercontent.com/74126199/161728117-22dbe102-ed36-4852-b865-d6b4fc137f26.png)

![Picture2](https://user-images.githubusercontent.com/74126199/161728147-7e9775d1-108c-4121-88b9-72d5f1d90e11.png)

![Picture3](https://user-images.githubusercontent.com/74126199/161728175-2f8dac2b-6b03-4d9a-9f28-ed661827b778.png)

```
line 210 app.js
line 215 app.js
line 499 app.js
```
For using routers , you need to change the path file on top lines.

Models Folder also is really necessary and you need to have it for your api.

# How it Works 

For authentication this api support two parts. if you want forget-password || reset-password you can do it easily with this api.Scroll than for more detail

- 1 . Register 

- 2 . Login 

# Request register part

For Register part please open your postman application first and send a **POST** request . 
The Address of api for register is below down . 
```
http://localhost:3000/register
```

In the body of request you need to add photo of user image that you got it from user register form . 

Like Image below.

![postman](https://user-images.githubusercontent.com/74126199/161726757-37e5039d-3b4f-426d-ae0a-529d140782bf.png)

# Response register part
```
{
    "age": number,
    "expression": feeling,
    "gender": gender,
    "token": randomToken,
}
```
- 1 . age key will be a number , age of the user .

- 2 . expression key will be a feeling that user had in image . 

- 3 . gender key will be female || male . 

- 4 . token key ! Most important key is token . as you know in database you know to have a id , token is id that it will be store in database and you can find user with that token

This data + Image Description (coordinate position of face points) will be stored in Database.json . 

For storing data we are using ``` node-json-db ```

- [node-json-db](https://www.npmjs.com/package/node-json-db)
- 
# Request login part

For login part please open your postman application first and send a **POST** request . 
The Address of api for login is below down . 
```
http://localhost:3000/login
```

In the body of request you need to add photo of user image that you got it from user login form . 

Like Image below.

![loginRequest](https://user-images.githubusercontent.com/74126199/161732118-498fbcdc-01dc-483c-89b6-e6b742574423.png)

# Response login part
```
{
    "faceMatch": bool,
    "token": a random token,
    "status": bool,
    "isTrusted": bool,
    "distance": Euclidean distance between the image stored in database and new image

}
```
- 1 . faceMatch key will be a bool that it will show that the face match was true || false .

- 2 . token key will be a token or a kind of id that it will be stored in database . 

- 3 . status key will be a bool that it will show that the operation performed successfully or no . 

- 4 . is trusted key will be a bool that will be show that you can trust the response or no . 

- 5 . distance key will be Euclidean distance between the image stored in database and new image

with token in response you can get user data such as **(age,feeling,gender)** from database.json

![getdata](https://user-images.githubusercontent.com/74126199/161734102-c158b1ca-4731-4f27-bdef-881afae05280.png)

Also you can see the response of login in your command line

# What is threshold ?

with Euclidean distance between the image stored in the database and the image in form we can underestand the distance.

```
const threshold = 0.50;
line 168 app.js
```
you can change the threshold but it's **not preferred**.
threshold less than 0.50 can make the api very sensetive but above 0.50 can make the security really weak.

# Frontend

if you don't know how to perform the frontend system and take photo from user image please look at link below.

[Frontend](https://github.com/Alireza17224/Simple-Frontend-Face-Detection-Api)


**This template is using [webcam-easy.js](https://www.npmjs.com/package/webcam-easy)**

# Contributions

**Face-Detection-Api** is an open-source package , so contributions are warmly welcome whether that be a code , docs or typo just fork it.

when contributing to code please make an issue for that before making your changes so that we can have a discussion before implementation.

# Give it a star

If this program was useful to you, please give this program a star so that others will trust our api faster .

# Problem

if you face any error please send the error in issues of github or in my email address **alirezamosavi4130@gmail.com**

I will solved it fast 

Thank you for reading
