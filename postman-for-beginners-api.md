# Postman Course API End Points Documentation

This API is a demo of Udemy Courses. You can access easily with the URL here -> **[https://postman-mehmetocal.duckdns.org/](https://postman-mehmetocal.duckdns.org/)** for welcome page


## Endpoints

- [Courses](#courses)
  - [Get All Courses](#1-get-all-courses)
  - [Get Details Of Course](#2-get-details-of-course)

- [Users](#users)
  - [Register](#3-register)
  - [Login](#4-login)

- [Comments](#comments)
  - [Get Your All Comments](#5-get-your-all-comments)
  - [Save New Comment](#6-save-new-comment)
  - [Delete a Comment](#7-delete-a-comment)
  - [Update a Comment](#8-update-a-comment)

## Courses

### 1. **Get All Courses**

- **URL**: `/courses`
- **Method**: `GET`
- **Description**: Retrieves a list of all courses.
- **Query Parameters**:

    | Parameter      | Type     | Required | Description                                                   |
    |----------------|----------|----------|---------------------------------------------------------------|
    | `instructor`   | `string` | No       | Filter Udemy courses by the instructor's name.               |
    | `isActive`     | `boolean`| No       | Filter courses based on their active status.                 |
    | `language`     | `string` | No       | Filter courses by the programming language used.             |
    | `starPoint`    | `double` | No       | Retrieve courses with a star rating equal to or higher than the specified value. |
    | `minPriceValue`| `double` | No       | Retrieve courses with a price equal to or higher than the specified minimum. |
    | `maxPriceValue`| `double` | No       | Retrieve courses with a price equal to or lower than the specified maximum. |

- **Example Request**:
  ```http
  GET /courses?instructor=Mehmet%20ÖCAL&isActive=true&language=Java&starPoint=4.2&minPriceValue=150&maxPriceValue=299.9
  Host: https://postman-mehmetocal.duckdns.org/
  Authorization: No Auth Required

[Back to top](#endpoints)



### 2. **Get Details Of Course**
- **URL**: `/courses/courseDetail`
- **Method**: `GET`
- **Description**: Retrieves a course with course Id.
- **Path Variable**:

    | Parameter      | Type     | Required | Description                                                   |
    |----------------|----------|----------|---------------------------------------------------------------|
    | `courseId`   | `string` | Yes       | Get details of any course with course Id              |

- **Example Request**:
  ```http
  GET /courses/courseDetail/UDEMY_COURSE_00000002
  Host: https://postman-mehmetocal.duckdns.org/
  Authorization: No Auth Required

[Back to top](#endpoints)



## Users

### 3. **Register**
- **URL**: `/auth/register`
- **Method**: `POST`
- **Description**: Create a new user with username and password.
- **Body**:

    | Parameter      | Type     | Required | Description                                                   |
    |----------------|----------|----------|---------------------------------------------------------------|
    | `email`   | `string` | Yes       | User email adress for registration              |
    | `password`   | `string` | Yes       | User password for registration              |

- **Example Request**:
  ```http
  POST /auth/register
  Host: https://postman-mehmetocal.duckdns.org/
  Authorization: No Auth Required

- **Example request body**:

  ```
  {
    "email": "example@gmail.com",
    "password": "example123"
  }
  ```

- **Example response**:

  ```
  {
    "message": "Kullanıcı başarılı şekilde oluşturulmuştur.",
    "accessToken": "asdfasdfasdfasdfa.asdfasdfasdfasdf.asdfasdf-asdfasdf-ML6aHd7dhRjwn-asdfasdf-asdfasdf-asfdasdf-asdfasdf"
  }
  ```

[Back to top](#endpoints)



### 4. **Login**
- **URL**: `/auth/login`
- **Method**: `POST`
- **Description**: Login with an exist user with username and password.
- **Body**:

    | Parameter      | Type     | Required | Description                                                   |
    |----------------|----------|----------|---------------------------------------------------------------|
    | `email`   | `string` | Yes       | User email adress for login              |
    | `password`   | `string` | Yes       | User password for login              |

- **Example Request**:
  ```http
  POST /auth/login
  Host: https://postman-mehmetocal.duckdns.org/
  Authorization: No Auth Required

- **Example request body**:

  ```
  {
    "email": "example@gmail.com",
    "password": "example123"
  }
  ```

- **Example response**:

  ```
  {
    "message": "Giriş başarılı.",
    "accessToken": "asdfasdfasdfasdfa.asdfasdfasdfasdf.asdfasdf-asdfasdf-ML6aHd7dhRjwn-asdfasdf-asdfasdf-asfdasdf-asdfasdf"
  }
  ```

[Back to top](#endpoints)



## Comments

### 5. **Get Your All Comments**
- **URL**: `/comments/getYourAllComments`
- **Method**: `GET`
- **Description**: Get your all comments.

- **Example Request**:
  ```http
  GET /auth/login
  Host: https://postman-mehmetocal.duckdns.org/
  Authorization: Bearer Token

- **Authorization**:

  | Parameter      | Type     | Required | Description                                                   |
  |----------------|----------|----------|---------------------------------------------------------------|
  | `Authorization`   | `string` | Yes       | Specifies the bearer token of the API client. |


[Back to top](#endpoints)



### 6. **Save New Comment**
- **URL**: `/comments/saveNewComment`
- **Method**: `POST`
- **Description**: Save a new comment.
- **Body**:

  | Parameter      | Type     | Required | Description                                                   |
  |----------------|----------|----------|---------------------------------------------------------------|
  | `courseId`   | `string` | Yes       | Unique identifier of the course you wish to comment on. |
  | `comment`   | `string` | Yes       | The text of your comment. Express your thoughts or feedback about the course |

- **Example Request**:
  ```http
  POST /comments/saveNewComment
  Host: https://postman-mehmetocal.duckdns.org/
  Authorization: Bearer Token

- **Authorization**:

  | Parameter      | Type     | Required | Description                                                   |
  |----------------|----------|----------|---------------------------------------------------------------|
  | `Authorization`   | `string` | Yes       | Specifies the bearer token of the API client. |

- **Example request body**:

  ```
  {
    "courseId": "UDEMY_COURSE_00000002",
    "comment": "Example Comment for a course."
  }
  ```

[Back to top](#endpoints)


### 7. **Delete a Comment**
- **URL**: `/comments/deleteAComment`
- **Method**: `DELETE`
- **Description**: Delete a comment.
- **Path Variable**:

  | Parameter      | Type     | Required | Description                                                   |
  |----------------|----------|----------|---------------------------------------------------------------|
  | `commentId`   | `string` | Yes       | Delete comment with comment Id. |

- **Example Request**:
  ```http
  DELETE /comments/deleteAComment/UDC_Y7ZZTPZ6OR
  Host: https://postman-mehmetocal.duckdns.org/
  Authorization: Bearer Token

- **Authorization**:

  | Parameter      | Type     | Required | Description                                                   |
  |----------------|----------|----------|---------------------------------------------------------------|
  | `Authorization`   | `string` | Yes       | Specifies the bearer token of the API client. |


[Back to top](#endpoints)



### 8. **Update a Comment**
- **URL**: `/comments/editComment`
- **Method**: `PATCH`
- **Description**: Update a comment.
- **Path Variable**:

  | Parameter      | Type     | Required | Description                                                   |
  |----------------|----------|----------|---------------------------------------------------------------|
  | `commentId`   | `string` | Yes       | Update comment with comment Id. |
  | `newComment`   | `string` | Yes       | New comment for exist comment. |

- **Example Request**:
  ```http
  PATCH /comments/editComment/UDC_Y7ZZTPZ6OR
  Host: https://postman-mehmetocal.duckdns.org/
  Authorization: Bearer Token

- **Authorization**:

  | Parameter      | Type     | Required | Description                                                   |
  |----------------|----------|----------|---------------------------------------------------------------|
  | `Authorization`   | `string` | Yes       | Specifies the bearer token of the API client. |


- **Example request body**:

  ```
  {
    "newComment": "Example new comment for exist comment."
  }
  ```

[Back to top](#endpoints)