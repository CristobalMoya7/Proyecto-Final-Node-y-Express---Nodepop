# API NODEPOP
Maintains advertisements for buying or selling items and allows searching by setting filters by various criteria such as:

- List of ads with the possibility of pagination. With filters by tag, type of ad (sale or search), price range (min. price and max. price) and item name
- List of existing tags
- Ad creation

# Technologies
Database is in Mongo DB 
Nodejs is use to build the proyect
NoSQLBooster 
PostMan


# Installation

Setted in environment variables for Android and IOS systems.
 ` "scripts": {
    "start": "cross-env NODEPOP_ENV=production node ./bin/www",
    "dev": "cross-env NODEPOP_ENV=development DEBUG=nodepop:* nodemon ./bin/www"
  } `

1.- Clone this repository.
2.- Run `npm install` to install the dependencies.
3.- Install nodemon `npm install nodemon --save-dev`
4.- Install Mongoose to give structure to MongoDB `npm install mongoose`
5.- Run dev mode in port 3000 by default: `npm run dev`


# Starting with API
* Warning!!!!
This command `npm run init-db` will erase the database and automatically load a couple of ads.

1.- Run npm run init-db to start THE API ONCE and automatically load a bunch of ads.
2.- Run npm run dev to access the API at http://localhost:3000.
3.- In NoSQLBooster the database will be created at localhost/dbadds/adds
4.- The schema is: name: String, sales: Boolean, price: Number, photo: String, tags: [String]
```JSON
 "_id": "65e3903571fd11524fe63bc9",
            "name": "Mercedes",
            "sales": false,
            "price": 40.000,
            "photo": "mercedes.jpg",
            "tags": [
                "vehicle"
            ],
```

# API routes and CRUD

Postman can be used to test the methods. 

## Filters

## Available Filters

### Filter by name:
```
- To filter by a specific product name, use the following URL:
  - `http://127.0.0.1:3000/api/adds?name=Audi`
  ```
```
- To search for a name containing a specific string, such as "au," in the product name, use:
  - `http://127.0.0.1:3000/api/adds?name=au`
```
### Filter by sales (boolean - true or false):
```
- You can filter by sales using:
  - `http://127.0.0.1:3000/api/adds?sales=true`
  ```

### Filter by price:
```
- To filter by a specific price, use:
  - `http://127.0.0.1:3000/api/adds?price=20000`
  ```

### Filter by price range (returns articles within that price range):
```
- You can specify a price range using the format "lowerPrice-higherPrice":
  - `http://127.0.0.1:3000/api/adds?priceRange=5000-30000`
  ```

### Filter by tags:
```
- To filter by tags, use one or more tags separated by "&":
  - `http://127.0.0.1:3000/api/adds?tags=vehicle&tags=powerful`
  ```

### Filter by ID:
```
- To filter by a specific ID, use the following URL:
  - `http://127.0.0.1:3000/api/adds/65e3903571fd11524fe63bc9`
  ```

### Sort by price ascending:
```
- To sort the results by price in ascending order, use:
  - `http://127.0.0.1:3000/api/adds?sort=price`
  ```

### Sort by price descending:
```
- To sort the results by price in descending order, use:
  - `http://127.0.0.1:3000/api/adds?sort=-price`
  ```

### Combination of filters:
```
- You can combine multiple filters, for example, filter by sales and tags:
  - `http://127.0.0.1:3000/api/adds?sales=true&tags=vehicle`
  ```

### Delete:
```
- To delete an advertisement, use the DELETE method and provide the ID of the advertisement you wish to delete:
  - `http://127.0.0.1:3000/api/adds/65e3903571fd11524fe63bdc`
  ```

## Postman Response
When sending a request to the API, expect to receive a response with a status 200.

# Validations
All included in routes/api/tags in the main method

# License
Final project Cristóbal Moya Lorente.
