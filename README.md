# XI RPL - Student API

This is a FastAPI application for managing student data.

## Requirements

Make sure you have the following installed:

- Python 3.x
- FastAPI
- Pydantic
- Jinja2
- pymongo
- bson

You can install the required packages using `pip`:

```bash
pip install fastapi[all]
pip install jinja2 pymongo
```

## Usage

1. Clone the repository:

```bash
git clone <repository_url>
cd <repository_folder>
```

2. Run the FastAPI application:

```bash
uvicorn index:app --reload
```

The API server will start, and you can access the API documentation and test it at `http://localhost:8000/docs`.

## API Endpoints

### `GET /home`

This endpoint returns the home page of the student API.

### `GET /`

This endpoint retrieves a list of all students.

### `POST /`

This endpoint creates a new student. It expects the following JSON payload:

```json
{
  "nisn": "string",
  "name": "string",
  "kelas": "XII" | "XI" | "X",
  "jurusan": "string",
  "jenis_kelamin": "Laki - laki" | "Perempuan"
}
```

### `PUT /{id}`

This endpoint updates the student data for a specific student ID. It expects the following JSON payload:

```json
{
  "nisn": "string",
  "name": "string",
  "kelas": "XII" | "XI" | "X",
  "jurusan": "string",
  "jenis_kelamin": "Laki - laki" | "Perempuan"
}
```

### `DELETE /{id}`

This endpoint deletes the student data for a specific student ID.

## Data Models

### `Student`

- `nisn` (str): The National Student Identity Number.
- `name` (str): The name of the student.
- `kelas` (str): The class of the student. Allowed values: "XII", "XI", or "X".
- `jurusan` (str, optional): The student's major or study program (if applicable).
- `jenis_kelamin` (str): The gender of the student. Allowed values: "Laki - laki" or "Perempuan".

## Helper Functions

The following helper functions are defined:

- `studentEntity`: Converts a student item from the database to a dictionary.
- `studentsEntity`: Converts a list of student items from the database to a list of dictionaries.

---

Please note that this README provides a basic overview of the student API and its endpoints. For more detailed information and data validation, refer to the API documentation available at `http://localhost:8000/docs` when the application is running.

For any issues or questions, feel free to contact the API maintainers. Happy coding!