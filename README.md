# moviesearch_flask_postman_json
Objective: The objective of this assignment is to create a Flask API that includes authentication using an API key. The API should allow users to retrieve movie details by sending a movie name to the API endpoint and also provide a list of all available movies. To accomplish this, you will utilise a free open-source movie data source.

Explanation about the code : -

This code is a Python Flask application that serves as an API for retrieving movie details from The Movie Database (TMDb) API. Let's break it down step by step:

1. The necessary imports are made, including the `requests` library for making HTTP requests, `Flask` for creating the web application, `request` for handling HTTP requests, `jsonify` for creating JSON responses, and `wraps` from `functools` for creating decorators.

2. An instance of the Flask application is created.

3. An API key is defined. This key is used to authenticate and authorize access to the TMDb API.

4. The `require_api_key` function is defined as a decorator. This decorator will be applied to routes that require an API key for access. It checks if the API key provided in the request headers matches the configured API key. If the API key is missing or incorrect, it returns an "Unauthorized" error response. If the API key is valid, it allows access to the decorated view function.

5. The `get_movie_details` route is defined with the route pattern `/movies/<movie_name>`. It is decorated with `@require_api_key` to require an API key for access. This route handles GET requests and retrieves details about a specific movie. It makes a request to the TMDb API to search for the movie using the provided `movie_name`. If a matching movie is found, it extracts relevant details such as title, release year, plot, cast, and rating. These details are returned as a JSON response. If no movie is found or there is an error, an error message is returned.

6. The `get_movie_list` route is defined with the route pattern `/movies`. It is also decorated with `@require_api_key` to require an API key for access. This route handles GET requests and retrieves a list of movies based on query parameters such as year, genre, and rating. It constructs the query parameters for the TMDb API request and makes the request to retrieve the movie list. It then extracts the relevant details from each movie, including the cast, and returns the list of movie details as a JSON response. If there is an error, an error message is returned.

7. The main entry point of the application is checked using `if __name__ == '__main__'`. If the script is executed directly, the Flask application is run in debug mode using `app.run(debug=True)`.

In summary, this code sets up a Flask API that requires an API key for accessing movie details. It provides two routes, one for retrieving details about a specific movie and another for retrieving a list of movies based on certain criteria.
8. We get the link on the output we post it on postman and send get request we get these outputs 
