# Product CRUD API

This is a simple RESTful API for performing CRUD (Create, Read, Update, Delete) operations on products, built using **Node.js**, **Express.js**, and **MongoDB**.


## Installation

Follow these steps to set up the application:

1. **Clone the repository** (or copy the code):
   ```bash
   git clone <repository_url>
   cd <project_folder>
   ```

2. **Install dependencies**:
   Make sure you have **Node.js** and **npm** installed on your machine. Then run:
   ```bash
   npm install
   ```

3. **Set up MongoDB**:
   - If you are using a local MongoDB instance, make sure MongoDB is installed and running on your machine.
   - Alternatively, you can use **MongoDB Atlas** for a cloud-based MongoDB instance.

---

## Environment Variables

If you are using MongoDB Atlas or any environment-specific configuration, create a `.env` file in the root directory and add the following variables:

```bash
MONGODB_URI=mongodb://localhost:27017/crud-api  # Use your MongoDB URI here
PORT=3000  # Port where the API will run
```

---

## API Endpoints

### Create Product
- **Method**: `POST`
- **URL**: `/products`
- **Body** (JSON):
    ```json
    {
      "name": "Product Name",
      "price": 100,
      "description": "Product description"
    }
    ```
- **Response** (JSON):
    ```json
    {
      "name": "Product Name",
      "price": 100,
      "description": "Product description",
      "_id": "product_id"
    }
    ```

### Get All Products
- **Method**: `GET`
- **URL**: `/products`
- **Response** (JSON):
    ```json
    [
      {
        "name": "Product Name",
        "price": 100,
        "description": "Product description",
        "_id": "product_id"
      }
    ]
    ```

### Get Product by ID
- **Method**: `GET`
- **URL**: `/products/:id` (replace `:id` with the actual product ID)
- **Response** (JSON):
    ```json
    {
      "name": "Product Name",
      "price": 100,
      "description": "Product description",
      "_id": "product_id"
    }
    ```

### Update Product
- **Method**: `PUT`
- **URL**: `/products/:id` (replace `:id` with the actual product ID)
- **Body** (JSON):
    ```json
    {
      "name": "Updated Product Name",
      "price": 120,
      "description": "Updated description"
    }
    ```
- **Response** (JSON):
    ```json
    {
      "name": "Updated Product Name",
      "price": 120,
      "description": "Updated description",
      "_id": "product_id"
    }
    ```

### Delete Product
- **Method**: `DELETE`
- **URL**: `/products/:id` (replace `:id` with the actual product ID)
- **Response** (JSON):
    ```json
    {
      "message": "Product deleted successfully"
    }
    ```

---

## Running the Application

1. **Start the server**:
   ```bash
   node server.js
   ```

2. By default, the server will run on port **3000**. You can access the API at `http://localhost:3000`.

---

## Testing the API

You can test the API using tools like **Postman**, **Insomnia**, or **cURL**.

### Sample cURL Commands

- **Create Product**:
  ```bash
  curl -X POST http://localhost:3000/products -H "Content-Type: application/json" -d '{"name": "Product Name", "price": 100, "description": "Product description"}'
  ```

- **Get All Products**:
  ```bash
  curl http://localhost:3000/products
  ```

- **Update Product**:
  ```bash
  curl -X PUT http://localhost:3000/products/<product_id> -H "Content-Type: application/json" -d '{"name": "Updated Product Name", "price": 120, "description": "Updated description"}'
  ```

- **Delete Product**:
  ```bash
  curl -X DELETE http://localhost:3000/products/<product_id>
  ```
