# Submission Reflection – Task Manager Codebase

## 1. Initial vs Final Understanding of the Codebase

### Initial Understanding

At the beginning, my understanding of the Task Manager codebase was quite surface-level. I recognized that it was a Node.js CLI application, and I could identify some files such as `cli.js`, `app.js`, `models.js`, and `storage.js`.

However, I was not fully clear on:
- How data flowed between modules
- The difference between business logic and storage logic
- Where new features should be implemented
- How the domain model influenced application behavior

I initially assumed most logic was centralized, rather than distributed across layers.

---

### Final Understanding

After working through the exercises, my understanding improved significantly.

I now understand that the system follows a **layered architecture**:

- **cli.js** → Handles user input and commands
- **app.js** → Contains business logic and rule processing
- **storage.js** → Handles data persistence (saving/loading tasks)
- **models.js** → Defines the structure of core entities like Task, TaskStatus, and TaskPriority

I now clearly understand:
- How tasks move through a lifecycle (todo → in_progress → review → done)
- How priority and status operate as independent dimensions
- How business rules should be implemented in `app.js`
- How filtering, tagging, and statistics are applied across the system

---

## 2. Most Valuable Insights from AI Prompts

### Feature Location Prompt

This prompt helped me understand:
- How to trace functionality across multiple files
- How CLI commands connect to business logic
- How storage operations are separated from application logic

It taught me how to systematically locate where new features should be implemented.

---

### Domain Model Prompt

This prompt was the most valuable for understanding the system deeply.

It helped me:
- Understand the Task entity as the central concept
- Learn the difference between status, priority, and tags
- Understand real business rules such as overdue logic and task lifecycle
- Connect technical code to real-world task management processes

---

### Pattern Recognition Guidance

This helped me identify:
- Reusable structures across features
- Common coding patterns (CRUD, filtering, file operations)
- How consistent architecture is maintained across modules

---

## 3. Approach to Implementing the New Business Rule

The new rule was:

> Tasks overdue for more than 7 days should be marked as abandoned unless they are high priority.

### My Approach

1. **Identify affected domain**
   - Recognized this as business logic, not CLI or storage logic

2. **Locate correct layer**
   - Determined that `app.js` is responsible for business rules

3. **Identify required changes**
   - Add new `abandoned` status in `models.js`
   - Implement rule logic in `app.js`
   - Ensure storage persists updated task state

4. **Define rule conditions**
   - Task must have a due date
   - Task must not be completed
   - Task must be overdue by more than 7 days
   - Task must not be high priority

5. **Consider execution point**
   - Rule should run when tasks are listed or statistics are generated

6. **Clarify assumptions**
   - Confirm definition of "high priority"
   - Confirm whether abandoned tasks are reversible

---

## 4. Strategies for Working with Unfamiliar Codebases

Through this exercise, I developed the following strategies:

### 1. Start with Structure First
I first identify key files and their responsibilities before reading logic in detail.

---

### 2. Trace One Feature End-to-End
Instead of reading everything at once, I follow one feature from:
CLI → Business Logic → Storage

---

### 3. Separate Layers of Responsibility
I now classify code into:
- Presentation layer (CLI)
- Business logic layer (app.js)
- Data layer (storage.js)
- Domain model (models.js)

---

### 4. Look for Patterns, Not Just Code
I focus on repeated structures such as:
- CRUD operations
- Filtering logic
- File read/write operations

---

### 5. Ask Domain-Focused Questions
Instead of only asking “how does this work?”, I ask:
- What does this mean in a real-world system?
- Why was this design chosen?
- What problem is this solving?

---

## Final Reflection

This exercise improved my ability to:
- Understand unfamiliar codebases quickly
- Identify system architecture patterns
- Translate technical code into business understanding
- Plan feature implementation logically before coding

I now feel more confident approaching real-world projects with structured thinking instead of guesswork.
