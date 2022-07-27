# Restaurant Menu Voting API

This is a REST API for voting restaurant menus.


## Getting Started


### Development



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

## API Endpoints

You can view the full [Postman Collection Here.](https://www.getpostman.com/collections/f11cb32c01901cee1a4c)

Some endpoints require a token for authentication. The API call should have the token in Authorization header.

    `{'Authorization': 'Bearer': <token>}`




| EndPoint                        |                 Functionality |
|:--------------------------------|------------------------------:|
| POST /api/v1/registration/      |               Register a user |
| POST /api/v1/create_employee/   |        Creates a new employee |
| POST /api/v1/login/             |                    User login |
| POST /api/v1/create_restaurant/ |             Create restaurant |
| POST /api/v1/upload_menu        |                      Add menu |
| GET /api/v1/restaurants/        |          List all restaurants |
| GET /api/v1/menu_list/          | List all menus of current day |
| GET /api/v1/vote/:id/           |                     Vote menu |
| GET /api/v1/results/            |       Show results of the day |

## Responses

The API responds with JSON data by default.


## Request examples

Request GET /api/v1/results/

curl -H "Authorization: Bearer <your_token>" -H "Content-Type: application/json" https://localhost:8000/api/v1/results/
