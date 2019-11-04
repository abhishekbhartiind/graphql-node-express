Intro to GraphQL
-------------------------------------------------------------------------

Installation:
    - yarn init
    - yarn add -D @babel/preset-env @babel/cli @babel/node @babel/core nodemon
    - yarn add express express-graphql graphql-tools mongoose
    
eq:
```
#GET_ALL_PRODUCT
{
  allProducts {
    title,
    _id,
    qty
  }
}

#CREATE_PRODUCT
mutation{
  createProduct(input: {
    title: "GraphQL Basic",
    qty: 2
  })
  {
    _id 
    title
    qty
  }
}

#GET_PRODUCT_ID
{
  getProduct(_id: "5dc017d8fdcfb41f7f1301ca"){
    title
    _id
    qty
  }
}

#UPDATE_PRODUCT
mutation{
  updateProduct(_id: "5dc017d8fdcfb41f7f1301ca", input: {
    title: "GraphQL Basic Update",
    qty: 2
  })
  {
    title
    qty
  }
}
#DELETE_PRODUCT
mutation{
    deleteProduct(_id: "5dc017d8fdcfb41f7f1301ca"){
        title
        qty
    }
}

Output: -------------------------------------------------------------------
{
  "data": {
    "allProducts": []
  }
}

Output: ------------------------------------------------------------------
{
  "data": {
    "createProduct": {
      "_id": "5dc017d8fdcfb41f7f1301ca",
      "title": "GraphQL Basic",
      "qty": 2
    }
  }
}

Output: --------------------------------------------------------------------
{
  "data": {
    "getProduct": {
      "title": "GraphQL Basic",
      "_id": "5dc017d8fdcfb41f7f1301ca",
      "qty": 2
    }
  }
}

Output: --------------------------------------------------------------------
{
  "data": {
    "updateProduct": {
      "title": "GraphQL Basic Update",
      "qty": 2
    }
  }
}
```