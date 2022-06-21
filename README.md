# go-movies-crud-backend
Application in Go for the backend for movies, using the CRUD operations. 
## Prerequsits 
Golang installed \
mux library, run in terminal: go get "github.com/gorilla/mux" \
Download Postman (for API management): https://www.postman.com/
## Running Application 
go run main.go \
Open Postman:
1. For  get all movies: Use GET operator to url http://localhost:8000/movies. Press Send to see all movies in the body.
2. For  creating a movie: Use POST operator to url http://localhost:8000/movies. In body write the movie you would like to add, for example 
    ```json 
    {
        "isbn": "77777",
        "title": "movie seven",
        "director": {
            "firstname": "Quentin",
            "lastname": "Tarantino"
        }
    }
    ```
3. For Updating a movie: USE PUT operator to url http://localhost:8000/movies/{id}, where id is the id of the movie you want to update. For example, to update movie with id 7 use http://localhost:8000/movies/7 and change body of to the desired content, for example: 
     ```json 
    {
        "isbn": "77777",
        "title": "movie seven",
        "director": {
            "firstname": "Martin",
            "lastname": "Scorsese"
        }
    }
    ```
4. For Deleting a movie: Use the DELETE operator to url http://localhost:8000/movies/{id}, where id is the id of the movie you want to update. For example, to delete movie with id 1 use http://localhost:8000/movies/1 and send the command. 