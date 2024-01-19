# JSON-SERVER
#when you want deploy your project with json-server on vercel or render mayby you will have problems to run your application becouse you use json server and need run this server to load your data for this reson you can use this code and create your endpoint to get post and other http requests
* Create a folder
```
mkdir json-server
cd json-server
```

#### Step 1: Create a node js project
```
npm init -y
```

#### Step 2: Install json server dependency
```
npm i json-server
```

#### Step 3: Create server.js
```js
const jsonServer = require('json-server')

const server = jsonServer.create()

const router = jsonServer.router('db.json')
const middlewares = jsonServer.defaults()
 
server.use(middlewares)
server.use('/api', router)
server.listen(process.env.PORT || 5000, () => {
  console.log('JSON Server is running')
})


```


#### Step 4: Create db.json
```js
{
  "articles": [
    {
      "id": 1,
      "title": "Example Article",
      "content": "This is an example."
    },
    {
      "id": 2,
      "title": "Second Article",
      "content": "This is also an example."
    },
    {
      "title": "Third Article",
      "content": "Another example!",
      "id": 3
    }
  ]
}
```

#### Step 5: Run the Node JS Project
```
node server.js
```

#### Step 6: Test - List Users API 
```
http://localhost:5000/api/articles
```


