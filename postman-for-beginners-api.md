# Postman Course API End Points Documentation

This API is a demo of Udemy Courses
You can access easily with the URL below for welcome page
**[https://postman-mehmetocal.duckdns.org/](https://postman-mehmetocal.duckdns.org/)** 


## Authentication
Most endpoints require an API key or token.

## Endpoints

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