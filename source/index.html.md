---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - javascript


includes:
  - errors

search: true
---

# Introduction

ToDo REST API Documentation

This page was created with [Slate](https://github.com/tripit/slate).

# ToDos

## Get All ToDos

```javascript

  $.ajax({
	  url: "/api/v1/todos",
	  dataType: "json",
	  type : "GET",
	  success : function(r) { }
	});

```

> The above command returns JSON structured like this:

```json
[
  {
    "id": "T001",
    "title": "title 001",
    "description": "description 001",
    "status": "PENDING"
  },
  {
    "id": "T002",
    "title": "title 002",
    "description": "description 002",
    "status": "PENDING"
  }
]
```

This endpoint retrieves all Todos.

### HTTP Request

`GET /api/v1/todos`

### Success Response

`Code: 200 OK`
`Content: [{}]`
  OR	
`Content:[{"id": "T001", "title": "Task 1", "description": "Task description 1", "status": "PENDING"},...]`

### Query Parameters

Parameter | Type    | Description
--------- | ------- | -----------
None      |         |

### Data Parameters

Parameter | Type    |Description
--------- | ------- |-----------
None      |         |

## Get a Specific ToDo

```javascript
	$.ajax({
	  url: "/api/v1/todos/T001",
	  dataType: "json",
	  type : "GET",
	  success : function(r) { }

	});
```

> The above command returns JSON structured like this:

```json
  {
    "id": "T001",
    "title": "title 001",
    "description": "description 001",
    "status": "PENDING"
  }
```

This endpoint retrieves a specific ToDo.

### HTTP Request

`GET api/v1/todos/:id`

### Success Response:

`Code: 200 OK`
`Content: {"id": "T001", "title": "Task 1", "description": "Task description 1", "status": "PENDING"}`

### URL Parameters

Parameter | Type    |Description
--------- | ------- |-----------
id        |  alphanumeric       |The ID of the ToDo to retrieve

### Data Parameters

Parameter | Type    |Description
--------- | ------- |-----------
None      |         |

## Create ToDo

```javascript
	$.ajax({
	  url: "/api/v1/todos",
	  dataType: "json",
    data {
      title: "Task 001"
      description: "description 001"
      status: 'PENDING'
    }
	  type : "POST",
	  success : function(r) { }

	});
```

> The above command returns JSON structured like this:

```json
  {
    "id": "T001",
    "title": "Task 001",
    "description": "description 001",
    "status": "PENDING"
  }
```

This endpoint creates ToDo.

### HTTP Request

`POST api/v1/todos/`

### Success Response:

`Code: 200 OK`
`Content: {"id": "T001", "title": "Task 1", "description": "Task description 1", "status": "PENDING"}`

### URL Parameters

Parameter | Type    |Description
--------- | ------- |-----------
id        |  alphanumeric       |The ID of the ToDo to retrieve

### Data Parameters

Parameter | Type    |Description
--------- | ------- |-----------
title        |  alphanumeric  |title of task
description | alphanumeric  | description of task
status  | Status  | status of task

## Update ToDo

```javascript
	$.ajax({
	  url: "/api/v1/todos",
	  dataType: "json",
    data {
      id: "T001"
      title: "Task 001 edit"
      description: "description 001 edit"
      status: 'DONE'
    }
	  type : "PUT",
	  success : function(r) { }

	});
```

> The above command returns JSON structured like this:

```json
  {
    "id": "T001",
    "title": "Task 001 edit",
    "description": "description 001 edit",
    "status": "DONE"
  }
```

This endpoint updates a specific ToDo.

### HTTP Request

`PUT api/v1/todos/`

### Success Response:

`Code: 200 OK`
`Content: {"id": "T001", "title": "Task 1", "description": "Task description 1", "status": "DONE"}`

### URL Parameters

Parameter | Type    |Description
--------- | ------- |-----------
None      |         |

### Data Parameters

Parameter | Type    |Description
--------- | ------- |-----------
id        | alphanumeric | id of task
title        |  alphanumeric  |title of task
description | alphanumeric  | description of task
status  | Status  | status of task

## Update Status ToDo

```javascript
	$.ajax({
	  url: "/api/v1/todos/T001/Status/DONE",
	  dataType: "json",
	  type : "PUT",
	  success : function(r) { }

	});
```

> The above command returns JSON structured like this:

```json
  {
    "id": "T001",
    "title": "Task 001 edit",
    "description": "description 001 edit",
    "status": "DONE"
  }
```

This endpoint updates the status of the specific ToDo.

### HTTP Request

`PUT api/v1/todos/:id/status/:status`

### Success Response:

`Code: 200 OK`
`Content: {"id": "T001", "title": "Task 1", "description": "Task description 1", "status": "DONE"}`

### URL Parameters

Parameter | Type    |Description
--------- | ------- |-----------
id        |alphanumeric       |id of task
status  | Status  | status of task

### Data Parameters

Parameter | Type    |Description
--------- | ------- |-----------
None      |         |


## Delete a Specific ToDo

```javascript
$.ajax({
	  url: "/api/v1/todos/00T1",
	  dataType: "json",
	  data: {}
	  type : "DELETE",
	  success : function(r) { }
	});	
```

> The above command returns JSON structured like this:

```json
{}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE /api/vi/todos/:id`

### Success Response:

`Code: 204 NO CONTENT`
`Content: {}`

### URL Parameters

Parameter | Type    | Description
--------- | ------- | -----------
id        |alphanumeric       |The ID of the ToDo to delete

### Data Parameters

Parameter | Type    |Description
--------- | ------- |-----------
None      |         |
