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

	Code: 200 OK
	Content:[{}]
	
  Code: 200 OK
	Content:[{"id": "T001", "title": "Task 1", "description": "Task description 1", "status": "PENDING"},{...},...]

### Query Parameters

Parameter | Type    | Description
--------- | ------- | -----------
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

	Code: 200 OK
	Content: {"id": "T001", "title": "Task 1", "description": "Task description 1", "status": "PENDING"}

### URL Parameters

Parameter | Type    |Description
--------- | ------- |-----------
id        |  alphanumeric       |The ID of the ToDo to retrieve


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

This endpoint delete a specific kitten.

### HTTP Request

`DELETE /api/vi/todos/:id`

## Success Response:

	Code: 204 NO CONTENT
	Content: {}

### URL Parameters

Parameter | Type    | Description
--------- | ------- | -----------
id        |alphanumeric       |The ID of the ToDo to delete

