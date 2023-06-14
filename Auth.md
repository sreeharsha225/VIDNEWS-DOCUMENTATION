# Handling Authentication

The Handling of Authentication is done in routes/api/auth.js file

### Register

For registering a user we will do a post request, The information of the user like name, email, password, phone Number etc,. are in the body on the request. We will check that the email exists in database or not, if exists we will not register and give an error message. if not exists then we will save this information in a instance of UserModel. we will hash the password before saving it database to keep passwords secure. After that we are making a JWT token using JWT with user id as a payload. we will return user and the token.

### Login

For login, We will use passport.authentiate to authentiate the loging with email and password. this passport.authentiate will do the passport local strategy, and returns if user is there for the given email and password then we will make a JWT token with payload as userid. it returns the user and token.