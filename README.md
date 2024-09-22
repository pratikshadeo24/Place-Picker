# PlacePicker

## Project Overview

The **PlacePicker** is a React-based application that allows users to create a personal collection of places they would like to visit or have visited. The app sorts available places by distance using geolocation and allows users to manage their selected places by adding or removing them from the list.

## Components

### 1. App
- Location: `src/App.jsx`
- The main component that handles state and renders the UI. It fetches the user's current location and sorts places by distance. It also handles adding and removing places from the user's collection.
  - Uses `useRef` to manage modal actions and `useState` to manage the list of available and picked places.
  - Leverages local storage to persist user selections between sessions.

### 2. Places
- Location: `src/components/Places.jsx`
- Displays a list of places, either "Available Places" or "I'd like to visit...", depending on where it is used.
  - Props:
    - `title`: The title for the list section (e.g., "Available Places").
    - `places`: An array of place objects to display.
    - `onSelectPlace`: A callback function triggered when a place is selected.

### 3. Modal
- Location: `src/components/Modal.jsx`
- A modal dialog component used to display content like the delete confirmation dialog.
  - Props:
    - `children`: The content inside the modal.
  - Methods:
    - `open()`: Opens the modal.
    - `close()`: Closes the modal.

### 4. DeleteConfirmation
- Location: `src/components/DeleteConfirmation.jsx`
- A component that confirms if the user wants to remove a place from their list.
  - Props:
    - `onConfirm`: Callback function triggered when the user confirms the deletion.
    - `onCancel`: Callback function triggered when the user cancels the action.

## Utility Functions

### sortPlacesByDistance
- Location: `src/loc.js`
- A utility function that sorts available places by distance from the user's current location based on latitude and longitude.

## Data

### AVAILABLE_PLACES
- Location: `src/data.js`
- An array of available places, each with attributes like `id`, `name`, and `location` (latitude and longitude).

## How to Install

1. Clone the repository:
    ```bash
    git clone <repository_url>
    cd PlacePicker
    ```

2. Install dependencies:
    ```bash
    npm install
    ```

3. Run the development server:
    ```bash
    npm run dev
    ```

## How to Use

1. When the app loads, it will ask for access to your location. This is used to sort the available places by their distance from your location.

2. The app displays two sections:
   - **Available Places**: Places sorted by distance from your current location.
   - **I'd like to visit...**: A list of places you have selected to visit.
   
3. To add a place to your collection, click on it in the "Available Places" list. The place will be added to the "I'd like to visit..." list.

4. To remove a place from your collection, click on it in the "I'd like to visit..." list. A confirmation dialog will appear, and upon confirming, the place will be removed from your list.

5. The app stores your selected places in the browser's local storage, so your selections persist between sessions.

## Example

You can select places from the "Available Places" list, and they will appear in your personal "I'd like to visit..." collection. You can remove them as needed.
