# Api_final

### Description
This API executes all CRUD operations for models **Post** and **Comment**.
Also it can execute **GET** and **POST** methods for models **Follow** and **Group**.

**Post** model consists of such fields as *text*, *pub_date*, *author* and *group*.
1. **text** is a _Text_ field for post's content. This field is **required**.
2. **pub_date** is a _DateTime_ field with a date of post's publication. This field fills in automatically.
3. **author** is a _Char_ field with maximal length of 200 symbols. This field fills in automatically with username of current user.
4. **group** is _Char_ field with maximal length of 200 symbols. This field isn't required but you can fill in this field with title of the group.

**Comment** model consists of such fields as *author*, *post*, *text* and *created*.
1. **author** is a _Char_ field with maximal length of 200 symbols. This field fills in automatically with username of current user.
2. **post**
