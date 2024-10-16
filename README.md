# Grocery Bud App

This is a simple **Grocery List App** built with React. The app allows users to add items to a list, mark them as completed, and remove items. It uses **localStorage** to persist the list across page reloads.

## Features

- **Add items** to the grocery list.
- **Mark items** as completed/uncompleted.
- **Remove items** from the list.
- List is **persisted** in the browser's `localStorage`.

## How it Works

The application consists of the following main components:

1. **App Component**:

   - Manages the state of the grocery list and the main logic for adding, removing, and editing items.
   - Uses `localStorage` to save and load the grocery list so that it persists even after refreshing the page.

2. **Form Component**:

   - A simple form that allows users to enter the name of a grocery item and submit it to be added to the list.

3. **Items Component**:

   - Displays all items in the list.
   - Each item can be removed or marked as completed.

4. **SingleItem Component**:
   - Represents a single grocery item with a checkbox to mark it as completed and a delete button to remove it.

### `localStorage` Usage

The app uses `localStorage` to store the grocery list, ensuring that the list persists between page reloads. Here’s how it’s integrated:

- **Saving to localStorage**:
  When a new item is added, edited, or removed, the updated list is saved to `localStorage` using the `setLocalStorage` function:

  ```js
  const setLocalStorage = (items) => {
  	localStorage.setItem("list", JSON.stringify(items));
  };
  ```

- **Loading from localStorage**:
  When the app is initialized, it loads the list from `localStorage`:

  ```js
  const defaultList = JSON.parse(localStorage.getItem("list") || "[]");
  ```

  This ensures that the user's grocery list remains available even after refreshing or reopening the browser.

## Installation

To run the project locally:

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/grocery-bud.git
   ```

2. Navigate to the project directory:

   ```bash
   cd grocery-bud
   ```

3. Install the dependencies:

   ```bash
   npm install
   ```

4. Start the development server:

   ```bash
   npm start
   ```

5. Open your browser and go to `http://localhost:3000` to view the app.

## Dependencies

- **React**: A JavaScript library for building user interfaces.
- **nanoid**: A library for generating unique IDs.
