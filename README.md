# Restaurant Menu Voting API

This is a REST API for voting restaurant menus.


## Getting Started


### Development

Uses the default Django development server.

1. Update the environment variables in the **docker-compose.yml** and **.env.dev** if you need.
2. Build the images and run the containers:

    $ docker-compose up -d --build`
3. Create migrations and apply them into database. NOTE the containers must be running:
      $ docker-compose exec web python manage.py makemigrations`
      $ docker-compose exec web python manage.py migrate`

4. Test it out at http://localhost:8000.

#### Running Tests in Development 

    $ docker-compose exec web python manage.py test
    
NOTE: Before you execute the command above. The containers must be up a running.

## API Features

1. Authentication
2. Creating restaurant
3. Uploading menu for restaurant (There should be a menu for each day)
4. Creating employee
5. Getting current day menu
6. Voting for restaurant menu
7. Getting results for the current day. 


### Dependencies Used

1. Django==4.0.6
2. djangorestframework==3.13.1
3. djangorestframework-simplejwt==5.2.0


[View all the other dependencies](.requirements.txt)

## API Versioning
You can pass the version of the application in the header
Example: {"Accept": "application/json; version=1"}
Supported versions: 1, 2
Default version: 2.


## API Endpoints

You can view the full [Postman Collection Here.](https://www.postman.com/collections/7f8ee5aa4d341f11646b)

Some endpoints require a token for authentication. The API call should have the token in Authorization header.

    `{'Authorization': "Bearer <token>"}`




| EndPoint                     |                 Functionality |
|:-----------------------------|------------------------------:|
| POST /api/registration/      |               Register a user |
| POST /api/create_employee/   |        Creates a new employee |
| POST /api/login/             |                    User login |
| POST /api/create_restaurant/ |             Create restaurant |
| POST /api/upload_menu        |                      Add menu |
| GET /api/restaurants/        |          List all restaurants |
| GET /api/menu_list/          | List all menus of current day |
| GET /api/vote/:id/           |                     Vote menu |
| GET /api/results/            |       Show results of the day |
| POST /token/refresh/         |      Refreshes your JWT token |

## Responses

The API responds with JSON data by default.


## Request examples

Request GET /api/results/

curl -H "Authorization: Bearer <your_token>" -H "Content-Type: application/json" https://localhost:8000/api/results/
