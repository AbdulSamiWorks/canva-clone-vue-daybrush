# Canva Clone: A Vue 3 exercise project for Fresh Trainees

This project is a simplified clone of Canva, built with Vue 3 + Vite. It provides a foundation for implementing design functionalities similar to Canva.

## Project Overview

The Canva Clone is a web application that allows users to create designs by adding, editing, and manipulating text, shapes, and images on the page. The application follows a familiar layout: a top bar, a left tool menu, and a main canvas area.

## Project Structure

```
src/
├── assets/             # Images, icons, and other static files
├── components/         # Vue Single File Components (SFC)
│   ├── TopBar.vue      # Top bar
│   ├── LeftMenu.vue    # Left tool menu
│   ├── CanvasArea.vue  # Main canvas area wrapper
├── App.vue             # Root layout
├── main.js             # App bootstrap
```

## DayBrush Moveable/Selecto understanding
Although you can write custom code to add/edit/delete/move elements, we recommend using DayBrush libraries to accelerate development.
- Selecto: https://github.com/daybrush/selecto
- Moveable: https://github.com/daybrush/moveable

These provide features to select, drag, resize, and rotate elements using mouse or touch.

## Getting Started

To run this project locally:

1. Clone this repository
2. Install dependencies with `npm install`
3. Start the development server with `npm run dev`
4. Open the URL printed by Vite (by default http://localhost:5173)

Optional:
- Build for production: `npm run build`
- Preview the production build: `npm run preview`

## Developer Requirements

Implement the following using Vue 3 (Composition API preferred) and a Select/Drag/Resize management library (e.g. DayBrush/Select).

### Functional Requirements (with FabricJS or similar)

1. Text Element
   - Add text to the canvas
   - Delete text from the canvas
   - Change font family
   - Change text color
   - Edit text content
   - Change font size
   - Apply text formatting (underline, bold, italic)

2. Shape Element
   - Add shapes (circle, square, rectangle) to the canvas
   - Delete shapes from the canvas
   - Change shape fill color
   - Change shape outline color
   - Resize shapes

3. Image Element
   - Add images by upload
   - Delete images from the canvas
   - Resize images
   - Apply opacity to images

4. Layers Functionality
   - Move layers up and down
   - Lock layers to prevent editing
   - Hide layers

### Non-Functional Requirements

1. Code should be clean, readable, and properly formatted
2. Follow the official Vue style guide where applicable
3. Ensure the application is responsive
4. Implement proper error handling
5. Write meaningful comments
6. Use proper naming conventions for variables, functions, and components

## Implementation Guidelines

- Use Vue 3 Composition API and SFCs (.vue files)
- Create reusable components
- Implement drag/resize/rotate using DayBrush Moveable/Selecto or FabricJS
- Use scoped CSS or CSS modules for styling (SFC <style scoped>)
- Ensure proper event handling for user interactions
- Keep state in components or consider a light store if needed (e.g., Pinia) — optional

## Available Scripts

- `npm run dev`: Runs the app in development mode (Vite)
- `npm run build`: Builds the app for production
- `npm run preview`: Serves the production build locally
