# Neighbourhood-DB
1. Consider the type of data we will be storing and therefore the type of database we should implement (SQL vs NoSQL)

✅SQL : 
Vertically scalable,which means they can be easily scaled up by adding resources such as CPUs or memory.

SQL database are efficient at processing queries and joining data across tables

Our data is highly structured, and that structure doesn’t change frequently
 
Making it easier to perform complex queries against structured data

Maturity wise SQL databases are built on mature technologies that are well known and supported by large developer communities.

As SQL database requires a predefined schema that determines how tables are configured and data is stored, resulting in a rigid structure that helps to optimize storage and ensure data integrity, but limits flexibility.

![image](https://user-images.githubusercontent.com/95479796/178716208-00116500-33ef-47be-a973-8fac001fc656.png)

API endpoints
1.       /houses
2.       /houses/address/
3.       /people
 
1.       A ‘SHOW’ RESTful request (using a get method) to display all of the houses in the area.
This will display the houses database, and SELECT * FROM houses.csv to display all of the houses with their addresses and owners.
Using the INSERT INTO houses (address,owner) VALUES (address value, owner value) will allow us to add more houses into the database if needed (for example if we forgot to add a house into the neighbourhood to begin with, or a new house could get built). This would then be integrated into a CREATE restful request with would post this into the /houses endpoint.
2.       Again, A ‘SHOW’ request(GET method) would be needed with a get method to display the Postcode and street address of the particular house.
Then we could update the address or postcode with Patch/Put methods if information was inputted wrong initially.
DESTROY restful request ( using the ‘DELETE’ HTTP verb) which can remove certain addresses.
 
3.       The SHOW request can be used to display all of the information on people (name, age , number of people in their household, houseid).
Then a CREATE request (using POST) can then add to these properties. If the number of people in the household changes, that number will need to be updated with ‘PATCH’ or ‘PUT’, and then the new person will need to be added with ‘POST’. Then a 'get' method on the /people endpoint could be used along with a search query:

SELECT people FROM neighbourhood WHERE age > 7;


STATUS CODES

CLIENT ERROR RESPONSES:

404 - This could arise from when a user inputs the wrong address id into the API endpoint.

400 - A bad request could arise if the user tries to access the wrong endpoint (e.g houses/people instead of /people).


SUCCESSFUL RESPONSES:

201: A successful put or patch request when a user updates an address

