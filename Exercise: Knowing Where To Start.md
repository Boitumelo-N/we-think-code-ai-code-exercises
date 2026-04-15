# WethinkCode – AI Code Exercises

## Exercise Part 1: Understanding Project Structure

## 2. Form Initial Understanding

The project appears to be a modular Node.js command-line (CLI) application designed for managing tasks.

The structure suggests the code is separated into different files, each responsible for a specific part of the system:
* app.js likely serves as the main entry point, starting and connecting the application components.
* cli.js likely handles command-line interactions and user commands.
* models.js likely defines the data structure for tasks.
* storage.js likely manages saving and retrieving task data.
* taskparser.js likely processes and interprets user input.
* taskpriority.js likely handles task prioritisation logic.
* tasklistmerge.js likely combines or organizes multiple task lists.

Overall, the system seems to follow a separation of concerns approach, where each file handles a specific responsibility.

### Technologies and Frameworks Used

Based on the package.json and project structure, the application likely uses:

* Node.js – runtime environment for running JavaScript outside the browser
* NPM – dependency and package manager
* Commander.js – used to build and manage CLI commands
* UUID – used to generate unique identifiers for tasks
* Jest – testing framework used to verify functionality

This indicates the project is a Node.js-based CLI tool with testing support.

### Main Components of the System

The main components of the application likely include:

* **CLI Interface (cli.js)**
Handles user input from the command line and defines available commands such as adding, listing, updating, or deleting tasks.

* **Application Entry Point (app.js)**
Initialises the application and connects the CLI layer with the underlying logic.

* **Data Model (models.js)**
Defines the structure of a task (e.g. id, title, status, priority).

* **Storage System (storage.js)**
Responsible for saving and retrieving task data, likely using file-based storage.

### Task Processing Modules
* taskparser.js → interprets and formats user input
* taskpriority.js → manages task priority logic
* tasklistmerge.js → merges or combines task lists

### Testing Layer

Uses Jest to ensure core functions work correctly and behave as expected.

The project follows a modular architecture, where each file has a clear responsibility. This improves maintainability, readability, and scalability of the codebase.

## 3. Apply the Project Structure Prompt

### Prompt Used:
I am a junior developer who has just joined this project. I have read the README but I still need help fully understanding the project structure and technology stack.

## Current Understanding
The project appears to be a modular Node.js command-line (CLI) application designed for managing tasks.

Based on the package.json, the project uses:
- Node.js (runtime environment)
- NPM (dependency manager)
- Commander.js (CLI command handling)
- UUID (unique ID generation)
- Jest (testing framework)

## Project Structure (My Understanding)
- app.js: likely the main entry point that starts the application
- cli.js: handles command-line interactions and user commands
- models.js: defines the structure of tasks
- storage.js: manages saving and retrieving task data
- taskparser.js: processes and interprets user input
- taskpriority.js: handles task prioritisation logic
- tasklistmerge.js: combines or organizes task lists

## Configuration File (package.json)
{
  "name": "TaskManager",
  "version": "1.0.0",
  "main": "cli.js",
  "scripts": {
    "test": "jest"
  },
  "dependencies": {
    "commander": "^9.0.0",
    "uuid": "^8.3.2"
  },
  "devDependencies": {
    "jest": "^29.5.0"
  },
  "private": true
}

## What I need help with
1. Validate my understanding and correct any misconceptions
2. Identify additional technologies or architectural patterns used
3. Explain the purpose of each file/module more accurately
4. Identify the actual application entry points
5. Suggest 3–5 questions I should ask to better understand the codebase

## My Confusion Areas
I am mainly unsure about how the modules interact with each other and how data flows through the application.

After your explanation, please suggest a small practical exercise I can do to confirm my understanding of the project structure.

### AI Response
I'll retrieve the actual project files to validate your understanding and provide accurate insights.Let me check the repository structure first:Based on the repository structure, I can see that **the exercise-analysis.md file you provided is the actual content of the repository**. This is your assignment document itself, not the source code you're analyzing. The document is asking you to understand a project structure (likely described elsewhere or that you need to examine).

Let me provide a comprehensive response based on your exercise document:

## Validation of Your Current Understanding

**You're on the right track!** Your initial analysis is solid for a modular CLI task management application. Here's where you're accurate and where we need to refine:

### ✅ What You Got Right:
- **Modular architecture**: Each file does handle a specific concern
- **Technology stack**: Node.js, Commander.js, UUID, and Jest are correctly identified
- **General purpose**: This is indeed a task management CLI tool
- **Separation of concerns principle**: You correctly identified this architectural pattern

### ⚠️ Refinements Needed:

1. **Entry Point**: The `package.json` shows `"main": "cli.js"`, so **cli.js is the entry point**, not app.js. However, app.js likely initializes and wires everything together.

2. **Data Flow**: The typical flow in this architecture would be:
   ```
   User Input (CLI) → CLI Parser → Task Parser → Business Logic → Storage → Display
   cli.js → taskparser.js → models.js/taskpriority.js → storage.js → Output
   ```

3. **File Responsibilities** (more accurate):
   - **cli.js**: Entry point + Command routing (probably uses Commander.js)
   - **app.js**: Application initialization and dependency wiring
   - **taskparser.js**: Converts raw user input into structured task objects
   - **models.js**: Task data structure/schema definitions
   - **taskpriority.js**: Priority calculation/sorting logic
   - **tasklistmerge.js**: Combines multiple task lists (useful for merging views or filters)
   - **storage.js**: File I/O operations (likely JSON file-based)



## Questions You Should Ask to Deepen Understanding

1. **How does Commander.js route commands?** What commands are available (add, list, update, delete)?
2. **What file format does storage.js use?** (JSON, CSV, plain text?)
3. **How do taskpriority.js and tasklistmerge.js interact?** Are they used together or separately?
4. **Is there any filtering or searching functionality?** Or just basic CRUD operations?
5. **How are errors handled?** Is there error handling in each module or centralized?



## Practical Exercise to Confirm Understanding

### Exercise: Trace the Data Flow

**Objective**: Follow a "add task" command from start to finish through the codebase.

**Steps**:
1. Open **cli.js** and find the "add task" command definition
2. Identify what parameters it accepts (title, priority, due date, etc.)
3. Trace what function gets called when the user executes this command
4. Follow that function into **taskparser.js** — what validation/transformation happens?
5. Check **models.js** — what does a task object look like?
6. See how **taskpriority.js** is involved (if at all)
7. Find the call to **storage.js** — what function saves the task?
8. Document: "When user types `[your-command] add 'Buy groceries' --priority high`, here's exactly what happens..."

**Expected Outcome**: Create a simple diagram showing:
```
User Input → CLI Command → Parser → Validation → Model → Priority Logic → Storage
```

**Deliverable**: Write a 2-3 paragraph explanation of this flow in your own words.


## Additional Architectural Insights

This architecture follows **layered architecture patterns**:
- **Presentation Layer**: cli.js (user interaction)
- **Application Layer**: app.js (coordination)
- **Business Logic Layer**: taskparser.js, taskpriority.js, tasklistmerge.js
- **Data Layer**: storage.js (persistence)
- **Data Model**: models.js (schema)

This is excellent for a learning project because each layer is independent and testable.

Would you like me to help you trace through a specific command or explain any particular module in more detail?

## Comparison and Reflection

### What AI confirmed
* The project follows a modular architecture with clear separation of concerns
* The application is a Node.js CLI tool using Commander.js for handling commands
* Different modules handle specific responsibilities such as parsing, storage, and task logic

### What I misunderstood or learned
* I initially thought app.js was the main entry point, but the AI clarified that cli.js is actually the entry point based on the package.json file
* I did not clearly understand how data flows through the application, but the AI explained the flow from CLI input to storage and output
* I had a general idea of file responsibilities, but the AI provided a more detailed and accurate breakdown of each module

### New insights gained
- The project follows a layered architecture (presentation, business logic, and data layers)
- The modules interact in a structured flow: CLI → Parser → Logic → Storage → Output
- Each file plays a specific role in maintaining clean and maintainable code

### How my understanding improved
My understanding improved from a general overview of the project structure to a more detailed understanding of how the components interact and how data flows through the system. I now have a clearer picture of the architecture and responsibilities of each module.

### Key takeaway
Using AI helped me validate my assumptions and quickly identify gaps in my understanding, especially around entry points and data flow within the application.

## 4. Documented Findings

### Misconceptions Identified
* I initially thought that `app.js` was the main entry point of the application. However, after reviewing the `package.json` file, I learned that `cli.js` is actually the main entry point.
* I assumed that most of the application logic was contained in one file, but I later understood that the project is modular and responsibilities are distributed across multiple files.
* I did not fully understand how data flows through the application, but I now see that it follows a structured flow from CLI input to processing and storage.



### Important Entry Points
* `cli.js` is the main entry point of the application, as specified in the `package.json` file.
* It is responsible for handling command-line input and routing commands to the appropriate logic.
* `app.js` likely serves as an initialization layer that connects different modules together.



### Architectural Patterns Identified
* The project follows a **modular architecture**, where each file has a specific responsibility.
* It also reflects a **layered architecture**, including:
  - Presentation Layer (CLI interface)
  - Business Logic Layer (task processing and prioritisation)
  - Data Layer (storage and persistence)
* The use of separation of concerns makes the codebase easier to maintain and extend.



### Key Components and Responsibilities

#### CLI Interface (`cli.js`)
* Handles user interaction through the command line
* Defines and processes available commands

#### Application Initialization (`app.js`)
* Connects different modules and initializes the application

#### Data Model (`models.js`)
* Defines the structure and properties of a task

#### Storage System (`storage.js`)
* Manages saving and retrieving task data

#### Task Parser (`taskparser.js`)
* Processes and interprets user input into structured data

#### Task Priority Logic (`taskpriority.js`)
* Handles prioritisation and sorting of tasks

#### Task List Management (`tasklistmerge.js`)
* Combines and organizes multiple task lists

## Exercise Part 2: Finding Feature Implementation

### Initial Search

### Search for Existing Export or File-Related Functionality

I reviewed the task manager codebase to determine whether any export or file-related functionality already exists, specifically focusing on features such as CSV export or external file generation.

The main files reviewed were:
- app.js
- cli.js
- models.js
- storage.js

The most relevant file is `storage.js`, which contains functions such as load and save, indicating that the system already performs file read and write operations for persistent storage of tasks.

However, no existing functionality was found that exports tasks into CSV format or any external file format designed for user download or data sharing.

### Data Transformation and External File Operations

The system already performs data transformation when converting user input into structured task objects. This likely occurs across multiple components:

- `cli.js` handles raw user input
- `models.js` defines the structure of a task object
- `storage.js` manages saving and retrieving structured data

The `storage.js` module is the main component responsible for external file operations, as it handles saving and loading task data from files.

This indicates that data is transformed from user input into structured objects before being stored externally.

### Reusable Utility Functions for File Operations

The `storage.js` file contains reusable functions that handle core file operations, including:
- Loading tasks from storage
- Saving tasks to storage
- Retrieving task data for processing

These functions can be reused for implementing a "Task Export to CSV" feature, as the export functionality would first require retrieving existing tasks before converting them into CSV format and writing them to a new file.

Therefore, `storage.js` acts as the primary utility module for file-based operations in the system.

## 2. Form a Hypothesis

### Where the Export Feature Might Belong

Based on my initial search, I believe the "Task Export to CSV" functionality would be implemented across multiple layers of the application.

- `storage.js` would handle the actual file writing and CSV formatting, since it already manages saving and loading data.
- `app.js` would act as the business logic layer, coordinating the export process by retrieving task data and passing it to the storage layer.
- `cli.js` would allow the user to trigger the export feature through a command.

This suggests that the feature would follow the existing pattern used by other functionalities in the system.

---

### Components That Might Need Modification

The following components would likely need to be modified:

- `storage.js`
  - To add functionality for converting task data into CSV format and writing it to a file

- `app.js`
  - To add a new method (e.g. exportTasksToCSV) that retrieves tasks and calls the storage function

- `cli.js`
  - To add a new command that allows users to export tasks from the command line

- `models.js`
  - May be used to ensure correct mapping of task fields into CSV format

---

### Search Terms Used

During my investigation, I used the following search terms:

- save
- load
- task
- file
- storage
- cli
- model
- export
- csv

---

### Files Identified

The following files were identified as relevant during the search:

- `storage.js` → handles file operations (saving and loading data)
- `app.js` → contains business logic for managing tasks
- `cli.js` → handles user interaction through commands
- `models.js` → defines the structure of task data

### Expected Flow:
User Command → cli.js → storage.js (get tasks) → CSV conversion → file output

This approach ensures the new feature integrates cleanly into the existing modular architecture.

### Existing Components That Would Need Modification

To implement the "Task Export to CSV" feature, the following components would need to be modified:

- `cli.js`: A new command (e.g. export) would need to be added to trigger the export functionality from the terminal.
- `storage.js`: This module would need to be extended to support exporting task data into CSV format in addition to existing save/load functionality.
- `models.js`: May need to be referenced to ensure task fields are correctly mapped into CSV columns (e.g. id, title, status, priority).

### Search Terms Used and Files Found

Search terms used during analysis:
- "storage"
- "save"
- "load"
- "task"
- "file"
- "cli"
- "model"
- "export"
- "csv"

Files identified in the codebase:
- `app.js` → application entry point
- `cli.js` → command-line interface and user commands
- `models.js` → task data structure definition
- `storage.js` → handles file read/write operations (most relevant file)

### Apply The Feature Location Prompt

### AI Prompt
I need to work on a "Task Export to CSV" feature in this codebase, but I am not sure where the implementation for this feature should live.

My current understanding:
- I searched for keywords such as save, load, task, file, cli, model, export, and csv
- I reviewed cli.js, storage.js, and models.js
- I believe storage.js is the most relevant file for file-related operations

Project structure:
- app.js
- cli.js
- models.js
- storage.js

Based on my search, storage.js seems to be the most relevant file, but I am unsure how the full feature should be implemented across the system.

I need help understanding:
1. Whether my search approach is correct and how it can be improved
2. Which files are most likely involved in implementing this feature
3. Better search terms or patterns to look for in the codebase
4. How different parts of this feature are distributed across the system
5. A step-by-step approach to locate and understand the full feature flow

### AI Response
I'll help you understand the codebase structure and guide you on implementing the "Task Export to CSV" feature. Let me first examine the files you've identified.Now I have a comprehensive view of your codebase. Let me provide you with structured guidance on implementing the "Task Export to CSV" feature:

## 1. Your Search Approach: ✅ Correct Direction, But Incomplete

Your search strategy was solid, but you missed one critical file: **app.js**. The complete architecture needs:
- `models.js` - Data structures (Task, TaskPriority, TaskStatus)
- `storage.js` - File I/O operations
- `app.js` - Business logic layer (TaskManager)
- `cli.js` - User interface

You should also search for: **"app"**, **"manager"**, **"export"**, and **"format"**.

## 2. Files Involved in the Export Feature

Here's the complete flow:

```
cli.js (new command)
    ↓
app.js (new TaskManager method)
    ↓
storage.js (new export method)
    ↓
CSV file output
```

## 3. Step-by-Step Implementation Approach

### **Step 1: Extend storage.js** (File I/O Layer)
Add a new method to handle CSV formatting and file writing:

```javascript
exportToCSV(outputPath = 'tasks.csv') {
  try {
    const tasks = Object.values(this.tasks);
    const headers = ['ID', 'Title', 'Description', 'Status', 'Priority', 'Tags', 'Due Date', 'Created At'];
    const csvRows = tasks.map(task => [
      task.id,
      `"${task.title}"`,
      `"${task.description}"`,
      task.status,
      task.priority,
      `"${task.tags.join(', ')}"`,
      task.dueDate ? task.dueDate.toISOString().split('T')[0] : '',
      task.createdAt.toISOString()
    ]);
    
    const csv = [headers, ...csvRows].map(row => row.join(',')).join('\n');
    fs.writeFileSync(outputPath, csv);
    return true;
  } catch (error) {
    console.error(`Error exporting to CSV: ${error.message}`);
    return false;
  }
}
```

### **Step 2: Check app.js for TaskManager** (Business Logic Layer)
You need to add a wrapper method in `TaskManager` that calls the storage method. Look for what `app.js` contains—it should have a `TaskManager` class that uses `TaskStorage`.

### **Step 3: Add CLI command** (User Interface)
Add a new command to `cli.js`:

```javascript
program
  .command('export <output_file>')
  .description('Export all tasks to CSV')
  .action((outputFile) => {
    if (taskManager.exportTasksToCSV(outputFile)) {
      console.log(`Tasks exported to ${outputFile}`);
    } else {
      console.log('Failed to export tasks to CSV.');
    }
  });
```

## 4. Better Search Patterns for Future Use

| Pattern | Purpose | Examples |
|---------|---------|----------|
| `symbol:` | Find class/function definitions | `symbol:export`, `symbol:TaskStorage` |
| `content:` with file type | Find usage patterns | `content:writeFileSync language:javascript` |
| Regex for methods | Find all methods in a class | `/export\|save\|write/` |
| Cross-file trace | Follow data flow | Track method calls from CLI → app → storage |

## 5. Architecture Summary

```
┌─────────────────────────────────────────────────────┐
│ CLI (cli.js) - User Commands                        │
│ - Parses input: node index.js export tasks.csv      │
└────────────┬────────────────────────────────────────┘
             │
┌────────────▼────────────────────────────────────────┐
│ Business Logic (app.js) - TaskManager               │
│ - Orchestrates operations                           │
│ - Calls storage methods                             │
└────────────┬────────────────────────────────────────┘
             │
┌────────────▼────────────────────────────────────────┐
│ Storage (storage.js) - TaskStorage                  │
│ - Handles file I/O (JSON and CSV)                   │
│ - Manages task data persistence                     │
└────────────┬────────────────────────────────────────┘
             │
┌────────────▼────────────────────────────────────────┐
│ Data Models (models.js)                             │
│ - Task, TaskStatus, TaskPriority                    │
└─────────────────────────────────────────────────────┘
```

## Next Steps

1. **Retrieve `app.js`** to see the full TaskManager implementation
2. **Add the `exportToCSV()` method to `TaskStorage`** in storage.js
3. **Add a wrapper in `TaskManager`** (from app.js)
4. **Add the CLI command** in cli.js
5. **Test with**: `node index.js export my-tasks.csv`

Would you like me to help you retrieve `app.js` and create the implementation files?

### Search Approach and Findings So Far

To investigate where a "Task Export to CSV" feature might be implemented, I explored the codebase using a keyword-based search approach combined with manual file inspection.

#### Search Approach:
- Searched for keywords such as: save, load, task, file, cli, model, export, csv
- Focused on identifying file-related operations and data handling logic
- Manually reviewed key files including:
  - cli.js
  - storage.js
  - models.js

#### Findings So Far:
- The most relevant file identified is `storage.js`, which handles saving and loading task data.
- `cli.js` appears responsible for handling user commands and would likely be where a new "export" command is added.
- `models.js` defines the structure of task data, which would be important for formatting CSV output.
- No existing CSV export functionality was found in the codebase.

Based on this, I believe the export feature does not currently exist and would need to be implemented using existing storage and task retrieval logic.

### AI Guidance on Locating Similar Features and Patterns

The AI explained that features in this codebase follow a consistent layered architecture pattern:

### 1. Core Architectural Pattern Identified
The system follows a three-layer structure:
- CLI Layer (`cli.js`) → handles user input and commands
- Business Logic Layer (`app.js`) → processes logic and coordinates actions
- Storage Layer (`storage.js`) → handles file reading and writing

### 2. How Existing Features Follow This Pattern
Existing commands such as listing and statistics follow this structure:
- CLI defines the command
- Business logic processes input and applies rules
- Storage layer retrieves or saves data

This pattern would also apply to a "Task Export to CSV" feature.

### 3. Feature Location Strategy
The AI suggested that when locating features, I should:
- Start by searching in `cli.js` for command definitions
- Trace function calls into `app.js` for business logic
- Follow data operations into `storage.js`
- Identify similar data transformation patterns (e.g. filter, map operations)

### 4. Key Patterns to Look For in Codebase
- `program.command()` → CLI commands
- `.action()` → command execution logic
- `fs.writeFileSync` / `fs.readFileSync` → file operations
- `.map()` / `.filter()` → data transformation
- Methods in `storage.js` → data persistence layer

### 5. Main Insight
The AI confirmed that new features like CSV export should follow the same layered flow:
CLI → Business Logic → Storage → Output

## 4. Document Your Findings

### 4.1 Feature Implementation Location

Based on my analysis of the codebase structure and AI guidance, the "Task Export to CSV" feature would be implemented across three main areas:

- **cli.js (Presentation Layer)**
  - A new command such as `export <filename>` would be added here.
  - This would allow users to trigger the export feature from the terminal.

- **app.js (Business Logic Layer)**
  - A new method such as `exportTasksToCSV()` would be added to handle the coordination of the export process.
  - This layer would retrieve task data and prepare it for formatting.

- **storage.js (Data Layer)**
  - A new function such as `exportToCSV()` would handle converting task data into CSV format and writing it to a file.
  - This is where file system operations would occur.



### 4.2 Related Components Affected

The following components would be affected or involved in implementing this feature:

- **models.js**
  - Provides the structure of task objects.
  - Ensures correct mapping of fields (id, title, status, priority, etc.) into CSV columns.

- **storage.js**
  - Handles data retrieval and file writing.
  - Would need to support CSV formatting in addition to existing JSON operations.

- **cli.js**
  - Would need to include a new command definition for exporting data.

- **app.js**
  - Would act as the intermediary between CLI input and storage operations.


### 4.3 Implementation Approach Plan

If I were to implement this feature, I would follow these steps:

1. **Investigate existing data retrieval methods**
   - Identify how tasks are currently fetched (e.g. getAllTasks or similar methods).

2. **Add CLI command**
   - Define a new command in `cli.js` called `export <filename>`.
   - Ensure it calls the appropriate method in the business logic layer.

3. **Add business logic method**
   - Create `exportTasksToCSV()` in `app.js`.
   - This method would retrieve all tasks and pass them to the storage layer.

4. **Implement CSV export in storage layer**
   - Add `exportToCSV()` in `storage.js`.
   - Convert task objects into CSV format.
   - Use file system operations to write the output file.

5. **Ensure data mapping is correct**
   - Use `models.js` to understand task structure.
   - Map fields properly into CSV columns.

6. **Test the feature**
   - Run the CLI command and verify the CSV file is correctly generated.
   - Check for formatting issues or missing fields.


### 4.4 Summary Insight

This feature follows the existing layered architecture of the system (CLI → Business Logic → Storage). By identifying existing patterns in the codebase, the new feature can be integrated without breaking the current structure, ensuring consistency and maintainability.

## Exercise Part 3: Understanding Domain Model

## 1. Extract Domain Model

### Core Entity Classes

The core entities identified in the task manager system are:

- **Task**
  - Represents a unit of work in the system
  - Contains properties such as id, title, description, status, priority, due date, and created date

- **TaskStatus**
  - Represents the current state of a task
  - Examples include: pending, in-progress, completed

- **TaskPriority**
  - Represents the importance level of a task
  - Examples include: low, medium, high
 
### Business Logic Related to Tasks

The system includes several business rules and operations related to task management:

- Creating tasks with unique identifiers
- Updating task attributes such as:
  - status
  - priority
  - due date
- Deleting tasks from the system
- Retrieving task details
- Adding and removing tags from tasks
- Filtering tasks based on:
  - status
  - priority
  - overdue status
- Generating statistics about tasks

These operations are mainly handled in `app.js`, which acts as the business logic layer of the application.

### Domain-Specific Terminology

The following terms are specific to this application:

- **Task** → a piece of work that needs to be completed
- **Status** → the current progress state of a task
- **Priority** → the level of importance assigned to a task
- **Due Date** → the deadline for completing a task
- **Overdue** → a task that has passed its due date without completion
- **Tag** → a label used to categorize or organize tasks

## 2. Form Initial Understanding

### Entity Relationships

The central entity in the system is the **Task**.

A Task is associated with:
- a **TaskStatus**, which represents its current progress
- a **TaskPriority**, which represents its importance level

Each task contains its own data such as title, description, due date, and tags.

The relationships can be summarized as:

Task → has a Status  
Task → has a Priority  
Task → may have Tags  
Task → may have a Due Date  

All operations performed on tasks (create, update, delete, retrieve) are managed through the application logic.

### Explanation of Each Entity

- **Task**
  - This is the main object in the system.
  - It represents a piece of work that the user wants to track and manage.

- **TaskStatus**
  - This defines the current state of a task (e.g. pending or completed).
  - It helps track progress.

- **TaskPriority**
  - This defines how important a task is.
  - It helps users decide which tasks to focus on first.
 
### Questions and Areas of Confusion

- How exactly are TaskStatus and TaskPriority implemented? (Are they enums, constants, or classes?)
- How are tags stored within a task? (As an array or another structure?)
- How does the system determine if a task is overdue?
- Is there validation when updating task fields such as status or priority?
- How do different modules (cli.js, app.js, storage.js) interact when performing task operations?

## 3. Apply Domain Understanding Prompt

### AI Prompt

I'd like you to act as a senior developer who deeply understands our codebase's domain model. I'm a junior developer trying to make sense of the business logic and domain concepts in this application.

Here's what I've found in the codebase:

- The main entity is a Task, which includes properties such as id, title, description, status, priority, due date, and tags
- There are related concepts such as TaskStatus and TaskPriority, which define the state and importance of a task
- The application includes functionality for creating, updating, deleting, and retrieving tasks
- Tasks can also be filtered by status, priority, or whether they are overdue
- Business logic appears to be handled in app.js, while storage.js handles saving and loading data

Based on this code, my current understanding is:
- The system seems to be modeling a task management application that allows users to track and manage their tasks
- I think Task, TaskStatus, and TaskPriority are related because each task has a status and a priority that define its state and importance
- The due date field appears to represent the deadline for completing a task, and is used to determine if a task is overdue
- I'm confused about how TaskStatus and TaskPriority are implemented (e.g. enums, constants, or classes)
- I'm also unsure how tags are stored and managed within a task

Could you, as a senior developer:
1. Validate my current understanding, correcting any misconceptions
2. Help me recognize the core domain concepts represented in this code
3. Explain the relationships between these entities in business terms, not just technical relationships
4. Clarify any domain-specific terminology or patterns I might be missing
5. Help me connect these models to actual user-facing features or business processes

Then, please ask me 3-5 questions that would test my understanding of this domain model. These should be questions that make me think about the business logic, not just the code syntax.

Finally, suggest a simple diagram I could sketch to visualize these relationships that would help solidify my understanding.

### AI Response
I'll help you deeply understand this domain model. Let me first examine the codebase to give you accurate insights.Let me try a different approach to explore the repository structure:Now let me fetch the key files:Excellent! Now I can give you a comprehensive senior-level review. Let me break this down for you.

## 1. Validating Your Current Understanding

**You got most things right!** Here's what you nailed and what needs refinement:

✅ **Correct:**
- Task is indeed the central entity
- TaskStatus and TaskPriority define task state and importance
- Due dates determine overdue status
- app.js handles business logic, storage.js handles persistence
- Tasks have CRUD operations

⚠️ **Needs Clarification:**
- **TaskStatus and TaskPriority are NOT enums or classes** — they're plain JavaScript objects (constant dictionaries). TaskPriority uses **numeric values** (1, 2, 3, 4) while TaskStatus uses **string values** ('todo', 'in_progress', 'review', 'done'). This distinction matters for filtering and querying.
- **Tags are stored as an array of strings**, not as separate objects. They're a flat collection directly on each Task.
- The **workflow is more sophisticated than just CRUD** — there's a specific lifecycle with timestamps (createdAt, updatedAt, completedAt) that tracks task history.

---

## 2. Core Domain Concepts

Here are the true domain concepts at play:

| Concept | Business Meaning | Implementation |
|---------|-----------------|-----------------|
| **Task** | A unit of work to be completed | Class with lifecycle |
| **Workflow State** | Where a task is in its journey (TODO → IN_PROGRESS → REVIEW → DONE) | TaskStatus enum with 4 states |
| **Urgency** | How quickly this task needs attention (LOW → MEDIUM → HIGH → URGENT) | TaskPriority enum with 4 levels |
| **Temporal Commitment** | When the task must be completed | dueDate field + isOverdue() logic |
| **Work Categories** | Contextual labels to group/filter related work | Tags array (e.g., "backend", "bug-fix", "client-request") |
| **Temporal Metadata** | Audit trail of when work happened | createdAt, updatedAt, completedAt timestamps |

---

## 3. Business Relationships Explained

Think of this NOT as a technical data model, but as **a work management system**:

**The Task Lifecycle:**
```
A user creates a Task (createdAt timestamp) 
→ Task starts in TODO state
→ User moves it to IN_PROGRESS (e.g., "I'm working on this now")
→ User moves it to REVIEW (e.g., "This needs approval")
→ User marks it DONE (special operation that triggers completedAt timestamp)
→ Completed tasks can be reviewed for metrics/statistics
```

**Why the distinction between TaskStatus and TaskPriority matters:**
- **Status** = "What stage is this work in?" (operational state)
- **Priority** = "How critical is this?" (business urgency)
- A task can be DONE (status) yet was HIGH priority (importance)
- You could have a LOW priority task stuck in IN_PROGRESS for weeks
- An URGENT task might move quickly through TODO → DONE

**The Overdue Concept:**
```
A task is "overdue" only if:
  1. It has a due date AND
  2. The due date has passed AND
  3. The task is NOT already done

This is critical because a completed task, no matter how late, 
shouldn't show as "overdue" anymore—it's resolved.
```

**Tags as Contextual Organization:**
Rather than forcing tasks into rigid categories, tags allow flexible, multi-dimensional organization:
- A task could be tagged: ["backend", "performance", "high-impact"]
- Same task could be tagged: ["sprint-42", "technical-debt"]
- Users can add/remove tags dynamically without restructuring the task

---

## 4. Domain-Specific Terminology You Should Know

- **Workflow/Pipeline**: The journey from TODO → DONE
- **Status Transition**: Moving a task from one state to another (e.g., marking IN_PROGRESS)
- **Completion Capture**: When you mark a task DONE, the system records *when* it was completed (completedAt)
- **Velocity Metrics**: The `stats` system tracks completed tasks in the last 7 days — this is used to measure team productivity
- **Overdue Tracking**: Tasks past their due date that aren't done yet — an early warning system
- **Categorical Filtering**: Slicing tasks by status, priority, or tags for different views

---

## 5. Business Processes This System Supports

1. **Daily Standup**: "What am I doing today?" → Filter by status (show IN_PROGRESS + TODO)
2. **Priority Triage**: "What fires do we need to put out?" → Filter by priority (show URGENT + HIGH) or show overdue
3. **Capacity Planning**: "How much have we completed?" → View `stats.completedLastWeek`
4. **Project Organization**: "Group work by theme" → Use tags (e.g., "feature-x", "bug-fix")
5. **Deadline Management**: "What's at risk?" → Show overdue tasks
6. **Progress Reporting**: "What's the status of everything?" → Count by status

---

## 6. Three Critical Questions to Test Your Understanding

**Question 1: The Overdue Logic**
> You have a task with priority URGENT and a due date of yesterday (April 11). The task is currently in REVIEW status. Your manager asks: "Is this task overdue?" What's the precise answer, and what does it tell you about the business rule?

**Question 2: Tag Management vs. Status**
> Why did the designers choose to use an array of tags instead of adding additional status values like `TaskStatus.BLOCKED` or `TaskStatus.WAITING_FOR_REVIEW`? What's the business advantage of this approach?

**Question 3: The Completion Timestamp**
> A task was created on April 1, moved to IN_PROGRESS on April 3, moved to REVIEW on April 5, and marked DONE on April 12. The due date was April 10. The updatedAt field gets reset each time it's modified. Why does the system separately track `completedAt` instead of just relying on `updatedAt`?

**Bonus Question 4: Statistics and Retention**
> The statistics function counts "Completed in last 7 days." What business value does this metric provide? When would a manager look at this number, and what decisions might they make based on it?

**Bonus Question 5: Priority Numbering**
> TaskPriority uses numeric values (1, 2, 3, 4) while TaskStatus uses strings ('todo', 'in_progress', etc.). Why do you think this design choice was made? What operation becomes easier with numbers that would be harder with strings?

---

## 7. Domain Model Visualization

Here's a diagram you can sketch to cement your understanding:

```
┌─────────────────────────────────────────────────────────┐
│                      TASK ENTITY                         │
│                                                          │
│  id: UUID                                               │
│  title: string ──────────────┐                          │
│  description: string         │ Basic Info               │
│  createdAt: timestamp ───────┘                          │
│                                                          │
│  ┌──────────────────────────────────┐                   │
│  │    LIFECYCLE STATE               │                   │
│  │  status: [TODO → PROGRESS →      │  Workflow         │
│  │           REVIEW → DONE]          │  Pipeline         │
│  │  updatedAt: timestamp             │                   │
│  │  completedAt: timestamp (if DONE) │                   │
│  └──────────────────────────────────┘                   │
│                                                          │
│  ┌──────────────────────────────────┐                   │
│  │    IMPORTANCE LEVEL              │                   │
│  │  priority: 1|2|3|4                │  Urgency         │
│  │  [LOW|MEDIUM|HIGH|URGENT]         │                   │
│  └──────────────────────────────────┘                   │
│                                                          │
│  ┌──────────────────────────────────┐                   │
│  │  TEMPORAL CONSTRAINTS             │                   │
│  │  dueDate: timestamp (optional)     │  Deadline        │
│  │  isOverdue(): boolean logic        │  Management      │
│  │  (dueDate < now && status ≠ DONE)  │                   │
│  └──────────────────────────────────┘                   │
│                                                          │
│  tags: [string, string, ...]         Flexible Labels    │
│                                                          │
└─────────────────────────────────────────────────────────┘

    WORKFLOW VISUALIZATION:
    
    [✓] Done           [>] In Progress        [?] Review
         ↑                    ↑                   ↑
         │                    │                   │
    [ ] Todo ─────────────────┴───────────────────┘
         
    ORTHOGONAL DIMENSIONS:
    
    Priority independent of Status:
    !!!! URGENT task stuck in TODO for weeks
    !    LOW priority task quickly DONE
    
    Tags cross-cut all statuses:
    Task1: [sprint-42, backend] → status: TODO, priority: HIGH
    Task2: [sprint-42, backend] → status: DONE, priority: LOW
    (Same tags, different states/priorities)
```

---

## Summary Table: Your New Mental Model

| Dimension | Values | Purpose | Use Case |
|-----------|--------|---------|----------|
| **Status** | TODO, IN_PROGRESS, REVIEW, DONE | Track work progression | "Where is this task in our process?" |
| **Priority** | 1, 2, 3, 4 (numeric) | Signal urgency | "What should I work on first today?" |
| **Due Date** | ISO date (optional) | Set deadline expectation | "Is this at risk?" |
| **Tags** | Free-form strings (multiple) | Flexible categorization | "Show me all backend work" or "What's in sprint 42?" |
| **Timestamps** | createdAt, updatedAt, completedAt | Audit trail & metrics | "How fast do we complete work?" |

You're now equipped to understand not just *how* the code works, but *why* it's designed this way. The domain model here is elegantly simple yet powerful enough to support real work management processes. Well done getting to this point! 🎯

## 4. Test Your Knowledge

### Question 1: Overdue Logic

Yes, the task is overdue.

This is because:
- The due date has passed (April 11)
- The task is not marked as DONE (it is still in REVIEW)

This shows that a task is only considered not overdue if it is completed, even if the due date has passed.

---

### Question 2: Tags vs Status

Tags are used instead of adding more status values because they provide more flexibility.

Status represents the stage of a task in the workflow (e.g. TODO, IN_PROGRESS, DONE), while tags allow tasks to be categorized in multiple ways without affecting the workflow.

Using tags allows a task to belong to multiple categories at once, such as "backend", "urgent", or "client-request", without complicating the status system.

---

### Question 3: completedAt vs updatedAt

The system uses `completedAt` instead of relying only on `updatedAt` because they serve different purposes.

- `updatedAt` changes every time a task is modified
- `completedAt` specifically records when a task was finished

This is important for tracking performance and measuring how long tasks take to complete.

---

### Question 4: Statistics and Retention

The "completed in last 7 days" metric helps measure productivity.

A manager might use this to:
- Track team performance
- Understand how much work is being completed over time
- Identify if productivity is increasing or decreasing

This helps in decision-making such as workload planning and performance evaluation.

---

### Question 5: Priority Numbering

Priority uses numbers instead of strings because numbers make comparison and sorting easier.

For example:
- It is easier to sort tasks by priority using numbers (1–4)
- The system can quickly determine which tasks are more urgent

This would be more difficult if priority was stored as text values.

## Revised Entity Diagram

Based on my improved understanding, the Task is the central entity and interacts with several key concepts.

Task:
- id
- title
- description
- status
- priority
- dueDate
- createdAt
- updatedAt
- completedAt
- tags (array)

Relationships:
- A Task has one Status (e.g. todo, in_progress, review, done)
- A Task has one Priority (e.g. low, medium, high, urgent)
- A Task may have multiple Tags
- A Task may have a Due Date

Key Logic:
- A task is overdue if the due date has passed and the task is not marked as done
- completedAt is only set when a task is marked as done

Simple Structure:

Task
 ├── Status (workflow stage)
 ├── Priority (urgency level)
 ├── Due Date (deadline)
 ├── Tags (labels/categories)
 └── Timestamps (createdAt, updatedAt, completedAt)

 ## Glossary of Domain Terms

- **Task**  
  A unit of work that a user wants to manage and track.

- **Status**  
  Represents the stage of a task in the workflow (e.g. todo, in_progress, review, done).

- **Priority**  
  Indicates how important or urgent a task is (e.g. low, medium, high, urgent).

- **Due Date**  
  The deadline by which a task should be completed.

- **Overdue**  
  A task that has passed its due date and is not yet completed.

- **Tags**  
  Labels used to categorize or organize tasks.

- **createdAt**  
  The timestamp when a task was created.

- **updatedAt**  
  The timestamp when a task was last modified.

- **completedAt**  
  The timestamp when a task was marked as done.

- **Workflow**  
  The progression of a task through different statuses.

- **Filtering**  
  The process of retrieving tasks based on conditions such as status, priority, or overdue state.

  # Exercise Part 4: Practical Application

## Scenario

The team needs to implement a new business rule:

> Tasks that are overdue for more than 7 days should be automatically marked as **abandoned**, unless they are marked as high priority.

---

## 1. Planning

### Files to Modify

Based on the project structure, the following files would need to be modified:

- **app.js**
  - Contains business logic
  - The new rule will be implemented here

- **models.js**
  - Add a new task status: `abandoned`

- **storage.js**
  - No major changes required
  - Will persist updated task data

- **cli.js** *(optional)*
  - May be updated to display or filter abandoned tasks

---

### Implementation Plan

To implement the new business rule:

1. **Update Task Status**
   - Add `abandoned` to TaskStatus in `models.js`

2. **Implement Business Logic**
   - In `app.js`, create a function that:
     - Retrieves all tasks
     - Checks if a task:
       - Has a due date
       - Is not marked as done
       - Is overdue by more than 7 days
       - Is not high priority
     - Updates the task status to `abandoned`

3. **Trigger the Rule**
   - Apply the rule when:
     - Listing tasks
     - Generating statistics
     - Or during application startup

4. **Persist Changes**
   - Save updated tasks using `storage.js`

---

### Questions for the Team

Before implementation, the following should be clarified:

- Does "high priority" include both HIGH and URGENT?
- Should abandoned tasks be reversible?
- When should this rule be triggered?
- Should abandoned tasks be visible in task listings?
- Should users be notified when tasks become abandoned?

---

## 2. Reflection

### How AI Prompts Helped

AI prompts helped in understanding the structure and flow of the application.

They made it easier to:
- Identify the separation of concerns (CLI, business logic, storage)
- Understand where new features should be implemented
- Recognize patterns in the codebase
- Trace how data flows through the system

---

### Remaining Uncertainties

Some areas that are still unclear:

- How frequently business rules should run in production systems
- Whether scheduling mechanisms exist in the application
- How error handling is consistently implemented
- Performance considerations with large datasets

---

### Next Steps

To improve understanding:

- Trace a full feature from CLI to storage
- Review how testing is implemented using Jest
- Practice implementing additional features
- Study error handling patterns in the codebase

---

## 3. Final Discussion and Reflection

### Group Discussion

My approach was to first identify key components and their responsibilities.

A challenge I encountered was understanding how modules interact.  
This was resolved by tracing function calls across:
- `cli.js`
- `app.js`
- `storage.js`

Using structured AI prompts helped guide the process and reduce confusion.

---

### Personal Reflection

#### Most Helpful Prompt

The most helpful prompt was the one focused on locating feature implementation, as it clarified where different logic belongs.

---

#### What I Would Do Differently

Next time, I would:
- Start by tracing one complete feature
- Focus on data flow earlier in the process

---

#### Additional Tools and Resources

To complement AI prompting:

- VS Code (search and navigation)
- Debugging tools
- Architecture diagrams
- Jest (testing framework)
