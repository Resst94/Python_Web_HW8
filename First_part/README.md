# The first part

## The order of execution

1. Create an Atlas MongoDB cloud database
2. Using the ODM Mongoengine, create models for storing data from these files in the authors and quotes collections.
3. When storing quotes, the author field in the document should not be a string value, but a Reference fields field
   where the ObjectID from the authors collection is stored.
4. Write scripts to upload json files to a cloud database.
5. Implement a script to search for citations by tag, author name, or set of tags. The script executes in an infinite
   loop and uses the usual input statement to accept commands in the following command:value format.
6. Output search results in utf-8 format only;

Example:
name: Steve Martin - find and return a list of all quotes by the author Steve Martin;
tag:life - find and return a list of quotes for the tag life;
tags:life,live - find and return a list of quotes that contain the life or live tags (note: no spaces between the life,
live tags);
exit - exit the script;

## Additional task

Think about and implement for the name:Steve Martin and tag:life commands the possibility of shortening the search
values as name:st and tag:li, respectively;
Cache the results of the name: and tag: commands using Redis so that when you make a second request, the search result
is taken from the cache instead of the MongoDB database;