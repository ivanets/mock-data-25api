# API DOCUMENTATION FOR "2K5 CABINET"

[![Build Status](http://travis-ci.com/ivanets/mock-data-25api.svg?branch=master)](http://travis-ci.com/ivanets/mock-data-25api)

 **Explore examples at [typicode.com](https://my-json-server.typicode.com/ivanets/mock-data-25api)**

> **Try: [mock-data-25api ->](https://my-json-server.typicode.com/ivanets/mock-data-25api)**

## Response Format

```js
{
    "status": "ok", // "ok" or "error" (error codesdescribed below)
    "data": { ... } // Response data
}
```

## API

| Type | Route | Headers | Request Data | Response (`data` field) | Example |
| ------ | ------ | ------ | ------ | ------ | ------ |
| **POST** | `/login` | `Content-Type: application/json` | `{ "phone": "74955454927", "password": "p@ssW0rd"  }` | `{ "token", "...", "user": { ... } }` | **[/login](https://my-json-server.typicode.com/ivanets/mock-data-25api/login)** |
| **GET** | `/streams` | `Authorization: {{ JWTToken }}` | | `{ "count": 0, "streams": [ ... ] }` | **[/streams](https://my-json-server.typicode.com/ivanets/mock-data-25api/streams)** |
| **GET** | `/bills/:stage_id` | `Authorization: {{ JWTToken }}` | | `{ "count": 0, "bills": [ ... ] }` | **[/bills/1](https://my-json-server.typicode.com/ivanets/mock-data-25api/bills/1)** or **[/bills/2](https://my-json-server.typicode.com/ivanets/mock-data-25api/bills/2)** |
| **GET** | `/stages` | `Authorization: {{ JWTToken }}` | | `{ "count": 0, "stages": [ ... ] }` | **[/stages](https://my-json-server.typicode.com/ivanets/mock-data-25api/stages)** |

 ### Global rules

| Type | Route | Response (`full`) | Example |
| ------ | ------ | ------ | ------ |
| **\*** | `*` | `{ "status": "error", "message": "..." }` | **[/error](https://my-json-server.typicode.com/ivanets/mock-data-25api/error)** |

## Error codes

> As HTTP response code

| HTTP Code | Description | Reason |
| ------ | ------ | ------ |
| 401 | Not authorized | Invalid JWT token in request `Authorization` header |
| 404 | Not found | There is no bills for stage 3, but requested: **[/bills/3](https://my-json-server.typicode.com/ivanets/mock-data-25api/bills/3)** |

### In all other cases

| HTTP Code | Description | Reason |
| ------ | ------ | ------ |
| 500 | Internal Server Error | |

### Todos

- Add tests
- Custom hosted specs
