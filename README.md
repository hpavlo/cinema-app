<h1 align="center">
  Cinema app 🎥
</h1>

<p align="center">
  <a href="#-description">Description</a> •
  <a href="#-features">Features</a> •
  <a href="#-architecture">Architecture</a> •
  <a href="#-technologies">Technologies</a> •
  <a href="#-how-to-start-the-program">How to start the program</a> •
  <a href="#-uml-diagram">UML diagram</a>
</p>

## 📃 Description
This is a simple server program designed to organize the operation of the cinema and supports all the most necessary functions, such as:

* New user registration and login for registered users
* Add and remove movies, movie sessions, and cinema halls
* Add the tickets to the shopping cart and complete the order

The program supports two types of roles: `ADMIN` and `USER`.
The user has the opportunity to view sessions, movies, manage their orders.
Admin can add or remove movies, sessions and so on.

Information is sent and received in `JSON` format.

## 🚀 Features
|  Role   | Possibility                                                                                      | Endpoints                                                                                                                                                                                                                                   |
|:-------:|:-------------------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `ADMIN` | Get and add movies, cinema halls<br/>Get, add and delete movie sessions<br/>Find users by email  | GET:`/cinema-halls`<br/>POST:`/cinema-halls`<br/>GET:`/movies`<br/>POST:`/movies`<br/>GET:`/movie-sessions/available`<br/>POST:`/movie-sessions`<br/>PUT:`/movie-sessions/{id}`<br/>DELETE:`/movie-sessions/{id}`<br/>GET:`/users/by-email` |
| `USER`  | Get movies, movie sessions and cinema halls<br/>Add tickets to shopping card<br/>Complete orders | GET:`/cinema-halls`<br/>GET:`/movies`<br/>GET:`/movie-sessions/available`<br/>GET:`/orders`<br/>POST:`/orders/complete`<br/>PUT:`/shopping-carts/movie-sessions`<br/>GET:`/shopping-carts/by-user`                                          |

There is also another endpoint for registering new users, which is available to everyone: `/register`
A user without an `ADMIN` role cannot perform operations, defined exclusively for users with `ADMIN` roles.


## ⚙ Architecture
|       3-layer architecture       |
|:--------------------------------:|
| Controllers (Presentation layer) |
|                ↓↑                |
|   Services (Application layer)   |
|                ↓↑                |
|     DAO (Data access layer)      |

## 🧑‍💻 Technologies
| Technology             | Version |
|:-----------------------|:--------|
| JDK                    | 11      |
| Maven                  | 4.0.0   |
| TomCat                 | 9.0.50  |
| MySQL                  | 8.0.22  |
| Spring (WEB, Security) | 5.2.2   |
| Hibernate              | 5.4.27  |

## 📎 How to start the program
1. Clone the project from GitHub
3. Configure [`/resources/db.properties`](https://github.com/pavlogook/cinema-app/blob/main/src/main/resources/db.properties#L2) with your own URL, username, password and JDBC driver
4. Configure Tomcat server (it is recommended to use [version 9.0.50](https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.50/bin/))
5. Run and enjoy the program 😉

## ✨ UML diagram
![UML diagram](img/uml.png)
