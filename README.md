Web development Interview Test
=====================

# Library management

Every DDL operation, should be done with SQL scripts, or migration if the chosen framework support it.

If you’re using migrations: follow the framework’s way to store data.
If you’re not using migrations: store sql files inside a folder: `migrations\scripts`; every script should be named with the following naming convention:

`<YYYYMMDD>_<incremental number>.sql`	e.g.: `20170925_001.sql`

The project backend should use the MVC pattern and communicate with Frontend using REST APIs. You can choose the language that you prefer (js, php, java, etc)

The application should have several controllers, split them as you think is better.

The frontend will be done in html and javascript and will communicate with backend with REST. It can be done as SPA or as a normal application, but the data should be fetched by xhr.
The css can be done with a framework (e.g. bootstrap) or not. You can use a css pre-processor, if using a pre-processor you will need to implement also some scripts to build the css.

## Database entities

* Book type (e.g. crime, novel, etc):
    * id – int
    * name - varchar(255)
    * active bit 0/1
* Book language
    * Like book type
* Book country
    * Like book type
* Book author
    * Id – int
    * Surname
    * First name
    * Date of birth
    * Date of death
    * City of birth
    * Country (reference to book country)
* Book
    * Id - int
    * Code – varchar(50)
    * Title – varchar(255)
    * Year – int
    * Type – reference to book type table
    * Language – reference to language table
    * Author – reference to author table

## Frontend 
The application will have a menu with the following voices:
* Configuration
    * Tipe
    * Language
    * Country
* Books
* Authors

### Author

The list will be paged and will show the following columns:
* Surname
* First name
* Date of birth
* Date of death
* City of birth
* Country (description, not code)
* Books no. (record counts of Book table); clicking on this field the user will go to the book view filtered by author
* Edit (will show the author details) 
* Delete (with confirmation, disabled when books no. > 0)

The table will be sortable and filterable, the country will use a dropdown.
There will be a “New” button that will allow to a add a new item to the list.

### Book

Similar to Author but columns will be:
* Code
* Title
* Year
* Book type (description) filterable with dropdown
* Language (description) filterable with dropdown
* Author (Surname + First Name) filterable with dropdown with link that will show the Author detail page
* Edit (will show the book details)
* Delete (with confirmation)

All tables should be editable and deletable (if there are no related items).

## Delivery
The project should be committed to a git repository inside your namespace, you will fork the source repository and work on that one.
