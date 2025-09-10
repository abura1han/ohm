# **Ohm Framework**

Ohm is a schema-driven, highly-extensible framework for rapidly building admin panels and control panels with Next.js and TypeScript.

## **The Vision**

The goal of Ohm is to eliminate the boilerplate involved in creating internal tools. By defining your data structures in a central configuration, Ohm automatically generates the necessary pages, forms, and input fields. It's built to be flexible, allowing for custom components and data persistence layers (adapters).

## **Core Concepts**

1. **Schema-Driven UI**: The UI is a direct reflection of your data schema. You define the shape of your data using Zod, and Ohm renders the appropriate forms. This ensures type safety and a single source of truth.  
2. **Collections as Pages**: Each top-level object in your configuration, called a Collection, automatically becomes a page in the admin panel (e.g., /panel/settings).  
3. **Documents as Sections**: Each document within a collection is rendered as an editable section or card on its respective page.  
4. **Extensible Adapters**: Ohm uses a simple adapter interface for data persistence. This allows you to start with an in-memory store for rapid prototyping and later switch to a production-ready database like MongoDB, PostgreSQL, or Firebase by simply changing the adapter.  
5. **Component Customization**: While Ohm provides default renderers for basic field types (string, boolean, number), you can easily provide your own custom React components for complex data types.

## **Project Structure**

* ohm.config.ts: The main configuration file. This is where you define all your collections and dashboard widgets.  
* lib/adapters.ts: Contains the DataAdapter interface and implementations (e.g., InMemoryAdapter).  
* app/panel/: The root directory for the admin panel UI.  
  * layout.tsx: The main layout with sidebar navigation.  
  * \[slug\]/page.tsx: The dynamic page that renders the UI for each collection.  
* components/ohm/: A directory for core Ohm components.  
  * FieldRenderer.tsx: Renders the correct input based on the field's schema type.  
  * DocumentSection.tsx: Renders a form for a single document.

## **Future Roadmap**

* \[x\] Initial schema-driven UI rendering.  
* \[x\] In-memory data adapter.  
* \[ \] MongoDB data adapter.  
* \[ \] SQL data adapter (e.g., Prisma).  
* \[ \] Dashboard and chart rendering (Chart.js, Recharts).  
* \[ \] Authentication and authorization layer.  
* \[ \] Custom field component registration.  
* \[ \] Advanced validation and feedback.
