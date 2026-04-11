WethinkCode – AI Code Exercises
Exercise Part 1: Understanding Project Structure

2. Form inital understanding:

The project appears to be a modular Node.js command-line (CLI) application designed for managing tasks.

The structure suggests the code is separated into different files, each responsible for a specific part of the system:
app.js likely serves as the main entry point, starting and connecting the application components.
cli.js likely handles command-line interactions and user commands.
models.js likely defines the data structure for tasks.
storage.js likely manages saving and retrieving task data.
taskparser.js likely processes and interprets user input.
taskpriority.js likely handles task prioritisation logic.
tasklistmerge.js likely combines or organizes multiple task lists.

Overall, the system seems to follow a separation of concerns approach, where each file handles a specific responsibility.

Technologies and Frameworks Used

Based on the package.json and project structure, the application likely uses:

Node.js – runtime environment for running JavaScript outside the browser
NPM – dependency and package manager
Commander.js – used to build and manage CLI commands
UUID – used to generate unique identifiers for tasks
Jest – testing framework used to verify functionality

This indicates the project is a Node.js-based CLI tool with testing support.

Main Components of the System

The main components of the application likely include:

CLI Interface (cli.js)

Handles user input from the command line and defines available commands such as adding, listing, updating, or deleting tasks.

Application Entry Point (app.js)

Initialises the application and connects the CLI layer with the underlying logic.

Data Model (models.js)

Defines the structure of a task (e.g. id, title, status, priority).

Storage System (storage.js)

Responsible for saving and retrieving task data, likely using file-based storage.

Task Processing Modules
taskparser.js → interprets and formats user input
taskpriority.js → manages task priority logic
tasklistmerge.js → merges or combines task lists

Testing Layer

Uses Jest to ensure core functions work correctly and behave as expected.

The project follows a modular architecture, where each file has a clear responsibility. This improves maintainability, readability, and scalability of the codebase.

3. Apply the Project Structure Prompt
