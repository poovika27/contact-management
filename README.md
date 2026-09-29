# Contact Management System

A RESTful Contact Management System built using **Node.js, Express.js, MongoDB, and Mongoose**.

## Technologies Used

* Node.js
* Express.js
* MongoDB
* Mongoose
* dotenv
* Nodemon
* Thunder Client

## Features

* Create a new contact
* View all contacts
* View a contact by contact ID
* Update contact details
* Delete contact
* Phone number validation
* Email format validation
* Unique contact ID
* Unique email
* Proper error handling

## Contact Fields

| Field       | Type   | Validation                           |
| ----------- | ------ | ------------------------------------ |
| `contactId` | String | Required, Unique                     |
| `name`      | String | Required                             |
| `phone`     | String | Required, Exactly 10 digits          |
| `email`     | String | Required, Unique, Valid email format |

## Project Structure

```text
contact-management/
│
├── models/
│   └── Contact.js
│
├── routes/
│   └── contactRoutes.js
│
├── .env
├── .gitignore
├── README.md
├── server.js
├── package.json
└── package-lock.json
```

## Installation

### 1. Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
```

### 2. Navigate to the Project Directory

```bash
cd contact-management
```

### 3. Install Dependencies

```bash
npm install
```

## Environment Variables

Create a `.env` file in the project root directory:

```env
MONGO_URI=your_mongodb_connection_string
PORT=5000
```

The application uses the following MongoDB database:

```text
contact_management
```

> **Note:** Do not share or upload your `.env` file because it contains your MongoDB connection details.

## Run the Application

### Development Mode

Run the application using Nodemon:

```bash
npm run dev
```

### Normal Mode

Run the application using Node.js:

```bash
npm start
```

The server runs at:

```text
http://localhost:5000
```

## API Endpoints

| Method   | Endpoint        | Description                 |
| -------- | --------------- | --------------------------- |
| `POST`   | `/contacts`     | Create a new contact        |
| `GET`    | `/contacts`     | Get all contacts            |
| `GET`    | `/contacts/:id` | Get a contact by contact ID |
| `PUT`    | `/contacts/:id` | Update a contact            |
| `DELETE` | `/contacts/:id` | Delete a contact            |

## API Usage

### 1. Create Contact

**POST**

```text
http://localhost:5000/contacts
```

#### Request Body

```json
{
  "contactId": "C001",
  "name": "Rahul Kumar",
  "phone": "9876543210",
  "email": "rahul@gmail.com"
}
```

#### Example Response

```json
{
  "message": "Contact created successfully",
  "contact": {
    "contactId": "C001",
    "name": "Rahul Kumar",
    "phone": "9876543210",
    "email": "rahul@gmail.com"
  }
}
```

### 2. Get All Contacts

**GET**

```text
http://localhost:5000/contacts
```

#### Example Response

```json
[
  {
    "contactId": "C001",
    "name": "Rahul Kumar",
    "phone": "9876543210",
    "email": "rahul@gmail.com"
  }
]
```

### 3. Get Contact by ID

**GET**

```text
http://localhost:5000/contacts/C001
```

#### Example Response

```json
{
  "contactId": "C001",
  "name": "Rahul Kumar",
  "phone": "9876543210",
  "email": "rahul@gmail.com"
}
```

### 4. Update Contact

**PUT**

```text
http://localhost:5000/contacts/C001
```

#### Request Body

```json
{
  "name": "Rahul Kumar Updated",
  "phone": "9876543211",
  "email": "rahul.updated@gmail.com"
}
```

#### Example Response

```json
{
  "message": "Contact updated successfully",
  "contact": {
    "contactId": "C001",
    "name": "Rahul Kumar Updated",
    "phone": "9876543211",
    "email": "rahul.updated@gmail.com"
  }
}
```

### 5. Delete Contact

**DELETE**

```text
http://localhost:5000/contacts/C001
```

#### Example Response

```json
{
  "message": "Contact deleted successfully"
}
```

## Validation

The application includes the following validation rules:

* `contactId` is required and must be unique.
* `name` is required.
* `phone` is required.
* `phone` must contain exactly 10 digits.
* `email` is required.
* `email` must have a valid email format.
* `email` must be unique.

## Error Handling

The application handles the following errors:

* Invalid phone numbers
* Invalid email formats
* Duplicate contact IDs
* Duplicate email addresses
* Contact not found
* Database errors
* Server errors

## Testing

All CRUD operations and validation cases were tested using **Thunder Client**.

The following operations were tested successfully:

* `POST /contacts`
* `GET /contacts`
* `GET /contacts/:id`
* `PUT /contacts/:id`
* `DELETE /contacts/:id`

The following validation cases were also tested:

* Invalid 9-digit phone number
* Invalid 11-digit phone number
* Invalid email format
* Duplicate contact ID
* Duplicate email
* Contact not found

## Database

MongoDB is used as the database, with Mongoose for schema definition, validation, and database operations.

**Database Name:**

```text
contact_management
```

## Dependencies

The project uses the following dependencies:

```text
express
mongoose
dotenv
nodemon
```

## Author

**Poovika M**
