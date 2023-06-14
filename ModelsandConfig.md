## Config

### db.js 

In this file we are connecting to the mongoDB database by mongoURI which is the URI to connect to mongoDB Atlas database.The reason for using mongoDB Atlas is it can be accessed from anywhere with this URI which has username and password for this database. but if we use local mongodb the populated data cannot be accessed by the other members from another computers.

### passport-strategy.js

For Authentication we use passport, the strategy we used here is the total strategy .Full code  and documentation of the strategies can be found in this link.[link for passport strategy documentation](http://www.passportjs.org/docs/downloads/html/)

### passportjwt.js

For protecting the requests we use JWT to know that user is logged in. passportjwt will decode the JWT and finds that the user is there in database or not. if there then userid will attach in to the request. The code and explaination is this link.[Link for passportjwt code and explaination](https://medium.com/front-end-weekly/learn-using-jwt-with-passport-authentication-9761539c4314)

## Models

these are MongoDB models

**The table will have models and their corresponding attributes**

| Model/filename                                               | Mongoose Schema   | Attributes                                                   |
| ------------------------------------------------------------ | ----------------- | ------------------------------------------------------------ |
| UserModel/User.js                                            | UserSchema        | firstname <br />lastname,<br />email<br />password<br />phone<br />avatar (profilePic)<br />place<br />city<br />stat<br />country<br />preferred language, <br />date(date of registration). |
| NewspaperModel/Newspaper.js                                  | NewspaperSchema   | avatar<br />title<br />description<br />noofsubscriptions( no of users subscribed the newspaper) |
| AvatarModel/Avatar.js                                        | AvatarSchema      | avatar<br />name<br />noofsubscriptions(no of times the avatar is used for subscribes newspaper)<br />user(if the avatar is uploaded then user attribute will have uploaded user's id otherwise it is null, if the user is there then this attribute refers to the user ) |
| MyNewspaperModel/MyNewspaper.js(This is a model for subscribing newspaper) | MyNewspaperSchema | newspaper(newspaperid that is subscribed, this refers to the Newspaper instatnce of NewspaperModel)<br />avatar(avatarid, this refers to the Avatar instance of Avatar Model)<br />user(id of the user who subscribed,refers to the user instance of userModel)<br />language(english,hindi etc)<br />voice(Male/female)<br />tags(ex;bussiness,political)<br />time(At what time we have to send the video) |

