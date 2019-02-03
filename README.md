# I'll Serve Soup 2

## Server and Database

### To start the server:

First, install all dependencies using yarn or npm before moving on.

Run _npm run server_ OR _yarn server_ to start. By default the server runs on port 5000. Once I deploy it, I will change this, of course.

Database Tables
[Inventory](#Inventory)|
[Users](#Users)|
[Locations](#Locations)|

Endpoints
[Inventory GET](#/inventory)|
[Users GET](#/users)|
[Locations GET](#/locations)|

---

# **Database Schema**

## Tables

Column names are _emphasized_

### Inventory

Used for managing total inventory and individual items. Able to Add items, remove items, update items AND get a list of the total inventory

-   Has an autoincrementing unique _*id*_ number
-   An item _*name*_ is required and must be unique, with a max length of 255 characters
-   A _*quantity*_ is optional. If you don't add a quantity, it will default to 0.
-   The _*units*_ are also optional. This would be useful for entering units of measure for ingredients. Can be anything and is made to be flexible for a soup kitchen that probably does not track the inventory down to the ounce. (example: "lbs" or "bags" for dry goods, "cans" for canned goods)

### Users

Used to manage list of users and individual users

-   Has an autoincrementing, unique ID number
-   A user _*username*_ is required and must be unique, max length 255 characters
-   A user _*password*_ is required, max length 255 characters
-   A user _*name*_ , max length 255 characters
-   A user _*role*_ is required, max length 128 characters (Though this will depend on whoever creates the registration form, here are some examples: "admin", "cook", "assistant", "manager", "volunteer", etc. )
-   A user _*email*_ , max length 255 characters
-   A user _*phone*_ , max length 128 characters

### Locations

Used to manage list of locations and individual locations

-   Has an autoincrementing, unique ID number
-   A _*name*_ is required and must be unique, max length 255 characters
-   A _*streetAddress*_, max length 255 characters
-   A _*city*_ , max length 255 characters
-   A _*state*_, max length 128 characters
-   An _*email*_ , max length 255 characters
-   A _*phone*_ , max length 128 characters

---

---

# **Endpoints**

_for axios calls_

## /inventory

#### GET

Returns a JSON object with the entire inventory

#### POST

The request body must include a unique name, and can optionally include quantity and units.

---

## /inventory/_{id}_

#### GET

Returns a JSON object with the corresponding item

#### PUT

The request body must include information to be updated

#### DELETE

Permanently removes the item from the inventory. A confirmation dialog may be a good idea here.

---

## /users

#### GET

Returns a JSON object with the entire users list. User must be logged in to access this.

REACT DEV >> _You need to have a way to retrieve the token that is generated._

---

## /users/register

#### POST

The request body must include a unique username and a password. It can optionally include a name, role, email, and phone number.

---

## /users/login

#### POST

The request body must include a unique username and a password matching what is on the database.

REACT DEV >> _You need to have a way to store the token that is generated. LocalStorage(setItem) is a simple way_

---

## /users/_{id}_

#### GET

Returns a JSON object with the corresponding user

#### PUT

The request body must include information to be updated

#### DELETE

Permanently removes the user from the database. A confirmation dialog may be a good idea here.

---

## /locations

#### GET

Returns a JSON object with the entire users list

#### POST

The request body must include a unique name, and can optionally include a streetAddress, a city, state, zipCode, email, and phone.

---

## /locations/_{id}_

#### GET

Returns a JSON object with the corresponding location

#### PUT

The request body must include information to be updated

#### DELETE

Permanently removes the location from the database. A confirmation dialog may be a good idea here.

---

---

---
