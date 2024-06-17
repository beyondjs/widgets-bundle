# BeyondJS Widgets Bundle

## Overview

The BeyondJS Widgets Bundle allows developers to create and manage UI components like pages and layouts using a widget
system. Widgets are self-contained, reusable components that can be rendered in various parts of the application,
providing a flexible and modular approach to building user interfaces.

## Features

-   **Reusable Components**: Create self-contained widgets that can be reused across different parts of the application.
-   **Layout and Page Widgets**: Support for creating layout widgets that define the structure of the application and
    page widgets for specific views.
-   **Configurable Properties**: Widgets can be customized through properties defined in the `module.json` file.
-   **Support for Multiple Processors**: Widgets can use different processors like TypeScript, Sass, HTML, Vue, Svelte,
    and more.

## How It Works

Widgets in BeyondJS are configured in the `module.json` file and processed to create reusable UI components. The widgets
can be registered, customized, and used throughout the application. The bundle handles the processing and registration
of these widgets, ensuring they are ready for use in the application.

### Configuration

To configure a widget bundle, you need to define it in your module's `module.json` file. Below is an example
configuration:

```json
{
	"name": "my-widget-bundle",
	"platforms": ["web"],
	"widget": {
		"element": {
			"name": "my-widget",
			"attrs": ["attr1", "attr2"]
		},
		"is": "page",
		"route": "/my-route",
		"render": {
			"csr": true,
			"ssr": false
		}
	}
}
```

### Key Properties

-   **`name`**: The name of the bundle.
-   **`platforms`**: Specifies the platforms the bundle supports.
-   **`widget`**: Contains configuration details specific to the widget.
    -   **`element`**: Defines the element name and attributes for the widget.
        -   **`name`**: The name of the custom element.
        -   **`attrs`**: An array of attributes that the element can accept.
    -   **`is`**: Specifies the type of widget, such as `layout` or `page`.
    -   **`route`**: Defines the route for page widgets.
    -   **`render`**: Specifies rendering options.
        -   **`csr`**: Client-side rendering (default is `true`).
        -   **`ssr`**: Server-side rendering (default is `false`).

## Types of Widgets

### Layout Widgets

Layout widgets define the overall structure of the application. They are used to create reusable layouts that can be
applied to different parts of the application.

Example configuration for a layout widget:

```json
{
	"name": "my-layout-bundle",
	"type": "widget",
	"platforms": ["web"],
	"widget": {
		"element": {
			"name": "my-layout",
			"attrs": ["attr1", "attr2"]
		},
		"is": "layout"
	}
}
```

### Page Widgets

Page widgets represent specific views or pages within the application. They can define their own routes and be rendered
independently.

Example configuration for a page widget:

```json
{
	"name": "my-page-bundle",
	"type": "widget",
	"platforms": ["web"],
	"widget": {
		"is": "page",
		"route": "/my-page"
        "element": {
			"name": "my-page",
			"attrs": ["attr1", "attr2"]
		}

	}
}
```

## Best Practices

-   **Naming Conventions**: Use meaningful names for widgets and attributes to make the code more readable and
    maintainable.
-   **Reusable Attributes**: Define reusable attributes for widgets to enhance modularity and flexibility.
-   **Consistent Configuration**: Maintain a consistent configuration structure in the `module.json` file for better
    readability and ease of maintenance.
