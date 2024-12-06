# Postman Course API End Points Documentation

This API is a demo of Udemy Courses
You can access easily with the URL below for welcome page
**[https://postman-mehmetocal.duckdns.org/](https://postman-mehmetocal.duckdns.org/)** 


## Authentication
Most endpoints require an API key or token.

## Endpoints

### 1. **Get All Users**
- **URL**: `/users`
- **Method**: `GET`
- **Description**: Retrieves a list of all users.
- **Query Parameters**:
  | Parameter | Type   | Required | Description          |
  |-----------|--------|----------|----------------------|
  | `page`    | `int`  | No       | Page number for pagination. |
  | `limit`   | `int`  | No       | Number of users per page.   |

- **Example Request**:
  ```http
  GET /users?page=1&limit=10 HTTP/1.1
  Host: api.example.com
  Authorization: Bearer YOUR_API_TOKEN