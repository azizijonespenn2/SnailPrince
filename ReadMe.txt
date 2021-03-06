/**
 * API that connects to MYSQL. Can be tested 
 * with postman, does not connect to HTML GUI
 * @ CSC131
 * @ team Snail Prince
 * @ authors Sharon Fitzpatrick John Geronimo Jordan Adelman
 * @ version 7
 *
 * --------------------------------------------------------------------------------------------
 *
 * Constants
 *
 * joi: Required to prove validation of JS objects.
 *
 * express: Used to make GET, POST, PUT, DELETE requests
 *
 * app: Represents application has GET, POST, PUT, DELETE
 *
 * mysql: Needed to access mysql database
 *
 * axios: Needed to gather data from the OMDB API
 *
 * CreateURL: This imports grab the functions from the util file
 *
 * Create_IMDB_URL: Also used to help create url with the import 
 *
 * config: constant with fields host, user, database, and password
 * Used to make connection to MYSQL
 * 
 * port: Dynamically asssigned. Enviromental variable is port otherwise assign to Port 3000.
 * 
 * sql: sql will be a string that holds the command to query the database
 * 
 * param: the parameter for sql query
 *
 * params: thhe parameters for sql query
 *
 * --------------------------------------------------------------------------------------------
 * 
 * Variables
 * 
 * server: sends a message in terminal to verify server is running
 *
 * --------------------------------------------------------------------------------------------
 *
 * Classes
 * 
 * Database
 *      Constructor
 *              @ param config: passes in config to connect to MYSQL
 *              @ return error if there is an error
 *      Query
 *              @ param sql constant mentioned above hoold queries for mysql
 *              @ param args arguments used to help create connection with query/communicate
 *              @ return error if there is an error
 *      Close
 *              @ return error if there is an error
 *            
 * --------------------------------------------------------------------------------------------
 *
 * Functions 
 *
 * async function GetRequest(url)
 * precondition: none
 * postconditions: Returns a json object that contains the year,title, and awards info for the movie 
 * @param{var} url created by function CreateUrl(name)
 * @return {var} jsonobject jsonobject of the movie in question
 *
 * async function Check_database_title(title)
 * Purpose: Finds the link to the imdb page based on the movie title given by the user.
 * @param{var} title the title of the movie
 * @return {var} title the title of the movie
 * @throw {error} if there is an error
 *
 * --------------------------------------------------------------------------------------------
 * 
 * Post Function
 *
 * app.post('/api/database/movie/post',(req, res) => POST request
 * preconditions: must be connected to database
 * postconditions: posted a movie with all its data into the mysl database
 * purpose: POST Request used to insert a movie created by user can only post if movie is a winner
 * @param {root} root of the directory where the movies are stored.
 * @param {req} request paramater from express to reuest data
 * @param {res} respond paraamter from express to send data
 *
 * --------------------------------------------------------------------------------------------
 *
 * Put Function
 *
 * app.put('/api/database/movie/put',(req, res) => PUT Request
 * preconditions: must be connected to database
 * postconditions: send the new data out to postman
 * purpose: searchs for the matching entry in the database based on entity
 * @param {root} root of the directory where the movies are stored.
 * @param {req} request paramater from express to reuest data
 * @param {res} respond paraamter from express to send data
 *
 * --------------------------------------------------------------------------------------------
 *
 * Delete Function
 *
 * app.delete('/api/database/movie/delete',(req, res) => DELETE Request
 * preconditions: must be connected to database
 * postconditions: send the deleted movie out to postman
 * purpose: searchs for the matching entry in the database based on entity and deletes the rows Collection endpoint
 * @param {root} root of the directory where the movies are stored.
 * @param {req} request paramater from express to reuest data
 * @param {res} respond paraamter from express to send data
 *
 * app.delete('/api/database/movie/delete',(req, res) => DELETE Request
 * preconditions: must be connected to database
 * postconditions: send the deleted movie out to postman
 * purpose: searchs for the matching entry in the database based on entity and deletes the rows Singleton endpoint
 * @param {root} root of the directory where the movies are stored.
 * @param {req} request paramater from express to reuest data
 * @param {res} respond paraamter from express to send data
 *
 * app.delete('/api/database/movie/delete',(req, res) => DELETE Request
 * preconditions: must be connected to database
 * postconditions: send the deleted movie out to postman
 * purpose: searchs for the matching entry in the database based on entity and deletes the rows Singleton endpoint
 * please note: Remeber collection delete request can delete rows of data it can endanger the database. Not for user use.
 * @param {root} root of the directory where the movies are stored.
 * @param {req} request paramater from express to reuest data
 * @param {res} respond paraamter from express to send data
 *
 * --------------------------------------------------------------------------------------------
 * 
 * Get Function
 *
 * app.get('/api/database/movies',(req,res) => GET request
 * precondintion: has to be connected to mysql
 * postconditions: sends the result of the get into postman
 * purpose: collection endpoint for movies
 * @param {root} root of the directory where the years are stored.
 * @param {req} request paramater from express to reuest data
 * @param {res} respond paraamter from express to send data
 *
 * app.get('/api/database/movie/year/:year',(req, res) => GET request
 * preconditions: has to be connected to mysql database
 * postconditions: send the result into postman
 * purpose: singleton endpoint for year
 * @param {root} root of the directory where the years are stored.
 * @param {req} request paramater from express to request data
 * @param {res} respond paraamter from express to send data
 *
 * app.get('/api/database/movies/years/:year',(req, res) => GET request
 * precondintion: has to be connected to mysql
 * postconditions: sends the result of the get into postman
 * purpose: collection endpoint for year
 * @param {root} root of the directory where the years are stored.
 * @param {req} request paramater from express to reuest data
 * @param {res} respond paraamter from express to send data
 *
 * app.get('/api/database/movie/category/:category',(req,res)=>GET request
 * precondintion: has to be connected to mysql
 * postconditions: sends the result of the get into postman
 * purpose: singleton enpoint for category
 * @param {root} root of the directory where the years are stored.
 * @param {req} request paramater from express to reuest data
 * @param {res} respond paraamter from express to send data
 *
 * app.get('/api/database/movies/categories/:category',(req,res)=>GET request
 * precondintion: has to be connected to mysql
 * postconditions: sends the result of the get into postman
 * purpose: collection endpoint for category
 * @param {root} root of the directory where the years are stored.
 * @param {req} request paramater from express to reuest data
 * @param {res} respond paraamter from express to send data
 *
 * app.get('/api/database/movie/winner/:winner',(req, res) => GET request
 * precondintion: has to be connected to mysql
 * postconditions: sends the result of the get into postman
 * purpose: singleton enpoint for winners
 * @param {root} root of the directory where the years are stored.
 * @param {req} request paramater from express to reuest data
 * @param {res} respond paraamter from express to send data
 *
 * app.get('/api/database/movies/winners/:winner' => GET request
 * precondintion: has to be connected to mysql
 * postconditions: sends the result of the get into postman
 * purpose: collection endpoint for winners
 * @param {root} root of the directory where the years are stored.
 * @param {req} request paramater from express to reuest data
 * @param {res} respond paraamter from express to send data
 *
 * app.get('/api/database/movie/entity/:entity',(req,res)=> GET request
 * precondintion: has to be connected to mysql
 * postconditions: sends the result of the get into postman
 * purpose: singleton enpoint entities
 * @param {root} root of the directory where the years are stored.
 * @param {req} request paramater from express to reuest data
 * @param {res} respond paraamter from express to send data
 *
 * app.get('/api/database/movies/entities/:entity',(req,res)=> GET request
 * precondintion: has to be connected to mysql
 * postconditions: sends the result of the get into postman
 * purpose: collection endpoint for entities. User can only provide the year,the category,the name of the entity, whether an award is won.
 * @param {root} root of the directory where the years are stored.
 * @param {req} request paramater from express to reuest data
 * @param {res} respond paraamter from express to send data
 *
 * app.get('/api/database/movie/years/:year1/:year2',(req, res) => GET request
 * preconditions: has to be connected to mysql database
 * postconditions: send the result into postman
 * purpose: gets a range of different years as a request
 * @param {root} root of the directory where the years are stored.
 * @param {req} request paramater from express to request data
 * @param {res} respond paraamter from express to send data
 * @throws {error} if there is an error, throws error
 *
 
 