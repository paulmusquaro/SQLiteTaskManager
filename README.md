# SQLiteTaskManager
SQLiteTaskManager is a simple task management system built using SQLite. It allows users to create, update, and manage tasks efficiently. The project includes three main tables: users, statuses, and tasks, with features like task assignment, status tracking, and task filtering based on various criteria. The system supports cascading deletions, ensuring that tasks are removed when users are deleted. Additionally, a `seed.py` script is provided to populate the database with random data using the Faker library. This project is perfect for learning how to implement CRUD operations, foreign key relationships, and basic SQL queries in a task management context.



## Features

- **Users**: Create users with unique names and email addresses.
- **Task statuses**: Tasks can have different statuses (e.g., "new", "in progress", "completed").
- **Tasks**: Create, edit, and delete tasks for users, linking them to statuses.
- **Relations**: Each task is associated with a user and has a status.
- **Queries**: Execute SQL queries to retrieve information about tasks, users, and statuses.

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/paulmusquaro/SQLiteTaskManager.git
    ```

2. Virtual Environment:

    + Activate `Poetry`:

        ```bash
        poetry shell
        ```

    + Install dependencies:

        ```bash
        poetry install
        ```


## Usage

### Create tables

The `create_table.py` script creates three tables: `users`, `status`, and `tasks`. To do this, simply run:

```bash
python create_table.py
```


### Add users and tasks

The `seed.py` script generates random users and tasks using the Faker library:

```bash
python seed.py
```

### Data selection

+ The `select.py` script is used to retrieve specific data from the SQLite database related to users and their tasks. When you run the script, it will execute a series of predefined SQL queries to fetch tasks based on various conditions, such as tasks by user, tasks by status, users without tasks, etc.:

    ```bash
    python select.py
    ```
+ **Modifying the Queries**:
    If you need to adjust any data selection logic (e.g., retrieving tasks with a different condition or adding a new filter), you can modify the corresponding SQL query in the `select.py` file. Each function is designed to handle a specific query, so changes to the logic will require editing the SQL statement inside the respective function.

### Update data
+ To update the status of a task, use:

    ```bash
    python update.py
    ```

### Delete data
+ To delete a task by its ID, run:

    ```bash
    python delete.py
    ```

## Project Structure

+ `connect.py`: Function for connecting to the database.
+ `create_table.py`: Script for creating tables in the database.
+ `delete.py`: Script for deleting tasks.
+ `insert.py`: Script for adding new tasks.
+ `seed.py`: Script for generating random users and tasks.
+ `select.py`: SQL queries for retrieving data.
+ `update.py`: Script for updating task statuses and user names.

## License

This project is open-source and available under the MIT License.