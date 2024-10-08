# Social Networking App Backend
Social Networking App , developed using Django Rest Framework (DRF) with essential functionalities such as user login/signup, user search, friend requests management, and user authentication.
>[![django](https://img.shields.io/badge/Django-092E20.svg?style=flat&logo=django&logoColor=white)](https://www.djangoproject.com/)
[![python](https://img.shields.io/badge/Python-3776AB.svg?style=flat&logo=Python&logoColor=white)](https://www.python.org/)
[![docker](https://img.shields.io/badge/Docker-2496ED.svg?style=flat&logo=Docker&logoColor=white)](https://hub.docker.com/r/zeroxeli/readme-ai)

---
# Functionalities:

- **User Authentication:** Users can sign up using a valid email format and log in with a case-insensitive email and password. All APIs, except login and signup, require authentication.
- **Search Users:** Search for users by search query.
- **Friend Requests Management:** Send, accept, or reject friend requests. Prevent users from sending more than 3 friend requests within a minute.
- **List Friends:** View a list of all accepted friend requests.
- **Pending Requests:** View a list of received friend requests pending acceptance.

---
# Steps To Follow
1. Clone the repository and move to project folder.
```sh
git clone https://github.com/Dhanshree019/Social-Netwoking-App-Backend.git
```
2. Open project folder in vscode or other IDE.
3. In folder structure, there is postman collection and environment file.
4. Import it in your postman portal.
> [!Note]
> If you have multiple environments, make sure to activate the required environment in the settings.

![image](https://github.com/user-attachments/assets/1200114f-c937-4fb8-ae0f-26aaf674debc)


5. In folder structure, there is Dockerfile and docker-compose.yml file.
6. Open terminal in vscode and run below command
```sh
docker-compose build
```
7. After Successfully build, up all services.
```sh
docker-compose up 
```
8. Test the api's and after testing down all services
```sh
docker-compose down
```

# API Endpoints
#### User Authentication:
- ${\color{lightgreen}\textnormal{POST}}$  /api/signup - Register a new user. \
  **Data**: JSON object with the following field
  - First name
  - Last name
  - Email
  - Password
- ${\color{lightgreen}\textnormal{POST}}$ /api/login - Login an existing user. \
  **Data**: JSON object with the following field
  - Email
  - Password

#### Search Users:
- ${\color{lightblue}\textnormal{GET}}$ /api/search?page={page_number}&keyword=(search_key) - Search users by search query.\
  **Query Params**: [ Authorize User ]
  - Page number
  - Search key

#### Friend Requests:
- ${\color{lightgreen}\textnormal{POST}}$ /api/friend-request/send - Send a friend request. \
  **Data**: JSON object with the following field [ Authorize User ]
  - Receiver Id
- ${\color{lightgreen}\textnormal{POST}}$ /api/friend-request/accept - Accept a friend request. \
  **Data**: JSON object with the following field [ Authorize User ]
  - Friend Request Id
- ${\color{lightgreen}\textnormal{POST}}$ /api/friend-request/reject - Reject a friend request. \
  **Data**: JSON object with the following field [ Authorize User ]
  - Friend Request Id
- ${\color{lightblue}\textnormal{GET}}$  /api/friends - List friends. [ Authorize User ]
- ${\color{lightblue}\textnormal{GET}}$  /api/pending-requests - List pending friend requests. [ Authorize User ]
