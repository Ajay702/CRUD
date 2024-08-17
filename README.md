# Flask CRUD Application with MongoDB

## Description
This project is a Flask application that performs CRUD (Create, Read, Update, Delete) operations on a MongoDB database for a User resource using a REST API. The application is designed to be scalable and uses Docker for containerization.

## Requirements
- Python 3.x
- Flask
- Flask-PyMongo
- Docker
- MongoDB

## Installation
1. Clone the repository:
    ```sh
    git clone <repository-url>
    ```
2. Navigate to the project directory:
    ```sh
    cd <project-directory>
    ```
3. Create a virtual environment:
    ```sh
    python -m venv venv
    ```
4. Activate the virtual environment:
    - On Windows:
        ```sh
        venv\Scripts\activate
        ```
    - On macOS/Linux:
        ```sh
        source venv/bin/activate
        ```
5. Install the required packages:
    ```sh
    pip install -r requirements.txt
    ```

## Deployment
1. Ensure Docker is installed and running on your machine.
2. Build the Docker image:
    ```sh
    docker build -t flask-crud-app .
    ```
3. Run the Docker container:
    ```sh
    docker run -d -p 5000:5000 --name flask-crud-app flask-crud-app
    ```
4. Open a web browser and navigate to `http://127.0.0.1:5000/`.

## Connecting to MongoDB
1. Ensure MongoDB is installed and running on your machine or accessible via a cloud service.
2. Update the MongoDB connection string in your Flask application configuration. Typically, this is done in a configuration file or directly in the application code:
    ```python
    from pymongo import MongoClient

    mongo_client = MongoClient("mongodb://localhost:27017/")
    db = mongo_client["your_database_name"]
    ```
3. Ensure the database and collection names match those used in your application.

## API Endpoints
- `GET /users` - Returns a list of all users.
- `GET /users/<id>` - Returns the user with the specified ID.
- `POST /users` - Creates a new user with the specified data.
- `PUT /users/<id>` - Updates the user with the specified ID with the new data.
- `DELETE /users/<id>` - Deletes the user with the specified ID.

## Testing with Postman
1. Open Postman.
2. Create a new request for each of the REST API endpoints.
3. Set the request method and URL for each endpoint:
    - `GET http://127.0.0.1:5000/users`
    - `GET http://127.0.0.1:5000/users/<id>`
    - `POST http://127.0.0.1:5000/users`
    - `PUT http://127.0.0.1:5000/users/<id>`
    - `DELETE http://127.0.0.1:5000/users/<id>`
4. For `POST` and `PUT` requests, set the request body to JSON and include the necessary fields (`id`, `name`, `email`, `password`).
5. Send the requests and verify the responses and database updates.

## License
This project is licensed under the MIT License.
