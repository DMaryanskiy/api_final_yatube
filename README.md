# Api_final

### Description
This API executes all CRUD operations for models **Post** and **Comment**.
Also it can execute **GET** and **POST** methods for models **Follow** and **Group**.

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
