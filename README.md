# Api_final

## Description
This API executes all CRUD operations for models **Post** and **Comment**.
Also it can execute **GET** and **POST** methods for models **Follow** and **Group**.
API uses **JWT** for authentication.

### Models

**Post** model consists of fields *text*, *pub_date*, *author* and *group*.
1. **text** is a _Text_ field for post's content. This field is **required**.
2. **pub_date** is a _DateTime_ field with a date of post's publication. This field fills in automatically with current time.
3. **author** is a _ForeignKey_ field which is related by Django's standard **User** model. This field fills in automatically with username of current user.
4. **group** is _ForeignKey_ field which is related by **Group** model. This field isn't required but you can fill in this field with title of the group.

**Comment** model consists of fields *author*, *post*, *text* and *created*.
1. **author** is a _ForeignKey_ field which is related by Django's standard **User** model. This field fills in automatically with username of current user.
2. **post** is a _ForeignKey_ field which is related by **Post** model. This field fills in automatically with *id* of the post you are commenting.
3. **text** is a _Text_ field for post's content. This field is **required**.
4. **created** is a _DateTime_ field with a date of post's publication. This field fills in automatically with current time.

**Follow** model consists of fields *user* and *following*
1. **user** is a _ForeignKey_ field which is related by Django's standard **User** model. This field fills in automatically with username of current user.
2. **following** is a _ForeignKey_ field which is related by Django's standard **User** model. This field fills in automatically with username of user you are trying to follow.

**Group** model consists of field *title*
1. **title** is a _Char_ field with maximal length of 200 symbols. This field is **required** and it represents a name of the group.

### Serializers

This API is working with 4 related by model serializers for each model. They also include _ReadOnlyField_ methods for _ForeignKey_ fields.
This method sends not all data in **JSON** format. It excludes extra information about user.

### Views

There were used **ViewSets** and **Generic** API classes.
Viewsets are really helpful to make **Post** and **Comment** models able to use **CRUD** operations by writing as less code as possible.
**Generics** were used to provide **Follow** and **Group** models with **List** and **Create** operations.
Also this API has some features to achieve control above this data

#### Filters

1. You may filter posts by groups they are participating
2. You may search user's followers and what current user follows

## Installation

To install this project you need
1. Clone this repository to your computer
2. Open terminal
3. Install virtual environment by using this command
`python -m venv name_of_environment_folder`
4. In case you are using **Visual Studio Code** you should open `preferences -> settings -> workspace`
5. Put into the search window `Python: Python Path`
6. Put your path for python `name_of_environment_folder\Scripts\python.exe`
7. Activate virtual environment `name_of_environment_folder\Scripts\activate.ps1`
8. Run your local server `python manage.py runserver`

## Examples

Input:

`GET: http://127.0.0.1:8000/api/v1/posts/{id}/`

Result:

```
{
  "id": 0,
  "text": "string",
  "author": "string",
  "pub_date": "2020-06-24T12:50:04Z"
}
```

Input:

`POST: http://127.0.0.1:8000/api/v1/group/`

Result:

```
{
  "title": "string"
}
```

Input:

`DELETE: http://127.0.0.1:8000/api/v1/posts/{post_id}/comments/{comment_id}/`

Result:

`204 NO CONTENT`
