#Run this 3 entries in Role table before hit any endpoint:
			#INSERT INTO roles(name) VALUES('ROLE_USER');
			#INSERT INTO roles(name) VALUES('ROLE_MODERATOR');
			#INSERT INTO roles(name) VALUES('ROLE_ADMIN');





1) signup :post
http://localhost:8080/api/auth/signup

body:
{

    "username":"yogendras",
    "password":"123456",
    "email":"yogendras@gmail.com",
    "role":["user","admin"]
}
response:
{
    "message": "User registered successfully!"
}

2)signIN:post
http://localhost:8080/api/auth/signin

body:
{

    "username":"yogendras",
    "password":"123456"
}

reponse:
{
    "id": 1,
    "username": "yogendra",
    "email": "yogendra@gmail.com",
    "roles": [
        "ROLE_USER"
    ],
    "accessToken": "eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJ5b2dlbmRyYSIsImlhdCI6MTY2MjAyMzMzMywiZXhwIjoxNjYyMTA5NzMzfQ.T3H3rkmcwFzHQipspDUvjCiHsCU0_MrwJ5KJkEnSHx-eKMLLzUjlw5Z-NopNyc3gOF7ijdCix8d5maH4_XGHrQ",
    "tokenType": "Bearer"
}


3) Get :http://localhost:8080/api/test/user
body: no body required only header with token key , application will extract the info from token key.

Header-
Authorization    Bearer eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJ5b2dlbmRyYSIsImlhdCI6MTY2MjAyMzMzMywiZXhwIjoxNjYyMTA5NzMzfQ.T3H3rkmcwFzHQipspDUvjCiHsCU0_MrwJ5KJkEnSHx-eKMLLzUjlw5Z-NopNyc3gOF7ijdCix8d5maH4_XGHrQ


response:
User Content.