

---

# React To-Do List with Asynchronous Programming

**Created by Fabricio Braga**  
**Last Updated: February 19th, 2025**

---

## Project Overview

This is a simple **To-Do List** application built with **React** that demonstrates **asynchronous programming** concepts such as **Promises**, **async/await**, and **Axios** for fetching data. The application allows users to:

1. Fetch a list of to-do items from a public API (JSONPlaceholder).
2. Add new to-do items (simulated locally).
3. Mark to-do items as completed.

---

## Features

- **Fetch To-Do Items**: Retrieve a list of to-do items from an external API.
- **Add New To-Do**: Add a new to-do item to the list (simulated locally).
- **Toggle Completion**: Mark a to-do item as completed or incomplete.
- **Asynchronous Programming**: Use of `async/await`, Promises, and Axios for handling asynchronous operations.

---

## Technologies Used

- **React**: A JavaScript library for building user interfaces.
- **Axios**: A promise-based HTTP client for making API requests.
- **CSS**: Basic styling for the application.
- **JSONPlaceholder API**: A free fake API for testing and prototyping.

---

## Prerequisites

Before running the project, ensure you have the following installed:

### 1. **Node.js and npm**

Node.js is a JavaScript runtime, and npm (Node Package Manager) is used to manage dependencies.

- **Install Node.js and npm**:
  - Download and install Node.js from [https://nodejs.org/](https://nodejs.org/).
  - Verify the installation:
    ```bash
    node -v
    npm -v
    ```

### 2. **Git (Optional)**

Git is used for version control. You can download it from [https://git-scm.com/](https://git-scm.com/).

---

## Getting Started

Follow these steps to set up and run the project locally.

### 1. **Clone the Repository**

Clone the repository to your local machine:

```bash
git clone https://github.com/hackthegap/course-6-async.git
cd course-6-async
```

### 2. **Install Dependencies**

Install the required dependencies using npm:

```bash
npm install
```

### 3. **Run the Application**

Start the development server:

```bash
npm start
```

The application will open automatically in your default browser at [http://localhost:3000](http://localhost:3000).

---

## Project Structure

Here’s an overview of the project structure:

```
course-6-async/
├── src/
│   ├── components/
│   │   ├── TodoList.js       # Component to display the list of to-do items
│   │   ├── TodoForm.js       # Component to add new to-do items
│   ├── App.js                # Main application component
│   ├── App.css               # Styles for the application
│   ├── index.js              # Entry point for the app
├── package.json              # Project dependencies and scripts
└── README.md                 # Project documentation
```

---

## Key Concepts

### 1. **Asynchronous Programming**

- **Promises**: Used to handle asynchronous operations like fetching data.
- **async/await**: Syntactic sugar for working with Promises, making asynchronous code look synchronous.
- **Axios**: A library for making HTTP requests.

### 2. **React Hooks**

- **useState**: Manages local state within a component.
- **useEffect**: Handles side effects like fetching data when the component mounts.

### 3. **Component-Based Architecture**

- **TodoList**: Displays the list of to-do items.
- **TodoForm**: Allows users to add new to-do items.

---

## Code Snippets

### Fetching To-Do Items

```javascript
useEffect(() => {
  const fetchTodos = async () => {
    try {
      const response = await axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5');
      setTodos(response.data);
      setLoading(false);
    } catch (error) {
      console.error('Error fetching todos:', error);
      setLoading(false);
    }
  };

  fetchTodos();
}, []);
```

### Adding a New To-Do Item

```javascript
const addTodo = (title) => {
  const newTodo = {
    id: Date.now(),
    title,
    completed: false,
  };
  setTodos((prevTodos) => [newTodo, ...prevTodos]);
};
```

### Toggling Completion Status

```javascript
const toggleCompletion = (id) => {
  setTodos((prevTodos) =>
    prevTodos.map((todo) =>
      todo.id === id ? { ...todo, completed: !todo.completed } : todo
    )
  );
};
```

---

## Available Scripts

In the project directory, you can run the following scripts:

- **`npm start`**: Runs the app in development mode.
- **`npm test`**: Launches the test runner.
- **`npm run build`**: Builds the app for production.
- **`npm run eject`**: Ejects the app from Create React App (advanced use only).

---

## Learning Objectives

This project covers the following key concepts:

1. **Asynchronous Programming**: Using Promises, `async/await`, and Axios.
2. **React Hooks**: Managing state and side effects with `useState` and `useEffect`.
3. **Component-Based Architecture**: Breaking the UI into reusable components.
4. **API Integration**: Fetching data from an external API.

---

## Contributing

If you'd like to contribute to this project, follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeatureName`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/YourFeatureName`).
5. Open a pull request.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

- This project was created as part of a course to teach asynchronous programming in React.
- Special thanks to [JSONPlaceholder](https://jsonplaceholder.typicode.com/) for providing a free fake API.

---

## Questions?

If you have any questions or need further assistance, feel free to reach out to the instructor or open an issue in the repository.

---
