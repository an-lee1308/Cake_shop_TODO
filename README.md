# Cake_shop_TODO
# Common
- Create table products
- API get /products => query database (select * from products) => return FE
# GET Request
- Level 0
  - Select neccessary fields
  - Map data using DTO
- Level 1
    - Pagination
    - Filter/sort/search
    - ex : /products?search=iphone&sort=price&order=ác&color=gold
- Level 4 Update performance with cache
    - Api get review products
    - Noone has any review => Data never change
    - problem state : Query once user navigate 
    - Solution : Cache and Invalidate cache when user add review
    - Flow
        - Get reivew
            - Check Cache exist (cacheKey)
            -   IF(TRUE) => get data from cache
            - IF(FALSE) => Query DB => Save Cache => return data FE
        - Add Review
            - Save result into Database
            - Invalidate cache (key)
            - Return response to FE
# POST/PUT/PATCH/DELETE Request
- Level 1
    - Validation
        - Always validate value to clean
        - Validate Frontend, Backend, Database
- Level 2
    - Soft Delete
        - Delete_At,isDelete
- Level 3 : Transaction
    - Create 1 order => minus amount product => create payment=> if products sold => error
# GENERAL request
- Correct RestfulAPI
- Correct HTTP request code
- Authentication and Authorization
- Level 3 Error handling and Logging
    - try catch and return error clear message
    - Log error in to file
- Level 4 Rate limit
    return 429
