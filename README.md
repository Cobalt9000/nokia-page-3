# Nokia Dashboard Page (for digital twin site.)

## Overview

This project is a Vue.js-based template for industrial applications. It provides a robust foundation for building complex, multi-pane user interfaces commonly used in industrial settings. The application features a customizable taskbar, menu bar, and a three-pane layout that can be easily adapted to various industrial use cases.

## Features

- Responsive taskbar with customizable items
- Flexible menu bar for additional navigation options
- Three-pane layout:
  - Left pane: Context-sensitive navigation
  - Middle pane: Main content area with fullscreen capability
  - Right pane: Additional information or controls
- Component-based architecture for easy customization and expansion
- Integrated Digital Site Twin view

## Getting Started

### Prerequisites

- Node.js (version 12.x or higher recommended)
- npm (usually comes with Node.js)

### Installation

1. Clone the repository:

```
git clone https://github.com/Cobalt9000/nokia-page-3.git
```

2. Navigate to the project directory:

```
cd nokia-page-3
```

3. Install dependencies:

```
npm install
```
or you can also use ```npm i``` for installing dependencies.

### Running the Application

To start the development server:

```
npm run dev
```

The application will be available at `http://localhost:5173` (or another port if 5173 is in use).

### Building for Production

To create a production build:

```
npm run build
```

The built files will be in the `dist` directory.

## Project Structure

- `src/`
  - `components/`: Vue components
  - `App.vue`: Main application component
  - `main.js`: Application entry point
- `public/`: Static assets
- `index.html`: HTML template

## Customization

### Adding New Views

1. Create a new component in the `components/` directory.
2. Import the component in `App.vue`.
3. Add a new case in the `handleViewSelected` method in `App.vue`.
4. Update the `ContextbarComponent` to include the new view option.

### Modifying the Layout

The main layout is defined in `App.vue`. You can adjust the pane sizes and behavior by modifying the CSS classes and component structure.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

If you have any questions or feedback, please open an issue in this repository.
