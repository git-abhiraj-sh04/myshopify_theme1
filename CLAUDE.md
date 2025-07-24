# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is **Nexus**, a Shopify theme based on the **Dawn theme v15.3.0**. It's a modern e-commerce theme built using Shopify's Liquid templating language, CSS, and vanilla JavaScript.

## Architecture & Structure

### Core Theme Architecture
- **Liquid Templates**: Uses Shopify's Liquid templating system for dynamic content rendering
- **Sections-based Layout**: Theme follows Shopify's sections architecture for flexible page building
- **Asset Organization**: CSS and JavaScript assets are organized by component with consistent naming conventions
- **Localization Support**: Multi-language support with extensive locale files (20+ languages)

### Directory Structure
```
/
├── assets/          # CSS, JS, and static assets (icons, images)
├── config/          # Theme settings and schema
├── layout/          # Base page layouts (theme.liquid, password.liquid)  
├── locales/         # Translation files for internationalization
├── sections/        # Reusable page sections and components
├── snippets/        # Reusable template fragments
└── templates/       # Page templates and customer account pages
```

### Key Components
- **Product System**: Comprehensive product display with variant handling, media galleries, and quick add functionality
- **Cart System**: Multiple cart types (drawer, page, notification) with live updates
- **Search**: Predictive search with configurable display options
- **Collections**: Advanced filtering and sorting capabilities
- **Customer Account**: Full customer portal with order management

## Theme Customization System

The theme uses a sophisticated settings system defined in `config/settings_schema.json`:
- **Color Schemes**: Dynamic color system with role-based color assignments
- **Typography**: Configurable font systems for headers and body text
- **Layout Controls**: Page width, spacing, and grid system configuration
- **Component Styling**: Borders, shadows, and corner radius settings for all UI elements
- **Animation Settings**: Scroll reveals and hover effects

## Development Guidelines

### File Naming Conventions
- **Components**: `component-[name].css/js` (e.g., `component-cart.css`)
- **Sections**: `section-[name].css` (e.g., `section-main-product.css`)
- **Templates**: `template-[name].css` (e.g., `template-collection.css`)
- **Icons**: `icon-[name].svg` with consistent naming

### CSS Architecture
- Component-based CSS with BEM-like methodology
- CSS custom properties used extensively for theming
- Responsive design with mobile-first approach
- Animation and transition system built-in

### JavaScript Architecture
- Vanilla JavaScript with ES6+ features
- Event-driven architecture using PubSub pattern (`pubsub.js`)
- Modular components with consistent initialization patterns
- Accessibility-first interactive elements

## Key Features

### E-commerce Functionality
- **Variant Selection**: Advanced product variant picker with swatches
- **Quick Add**: Bulk ordering and quick add to cart functionality
- **Cart Management**: Real-time cart updates with drawer/notification systems
- **Search & Filter**: Faceted search with price ranges and collection filtering
- **Product Media**: Advanced media gallery with zoom and model viewer support

### Customization Features
- **Theme Settings**: Extensive customization through Shopify admin
- **Section Groups**: Header and footer section groups for flexible layouts
- **Color Schemes**: Multiple color schemes with automatic role assignment
- **Typography**: Font picker with scaling options

### Performance Optimizations  
- **Asset Loading**: Deferred JavaScript loading for non-critical scripts
- **Image Optimization**: Responsive images with proper sizing
- **CSS Organization**: Component-based CSS for efficient loading
- **JavaScript Modules**: Modular JavaScript with lazy loading where appropriate

## Development Commands

This is a Shopify theme, so development typically involves:

### Shopify CLI Commands
```bash
# Start development server
shopify theme dev

# Deploy to theme
shopify theme push

# Pull latest theme
shopify theme pull

# Watch for changes
shopify theme dev --store=your-store.myshopify.com
```

### Theme Validation
```bash
# Check theme for issues
shopify theme check

# Lint Liquid templates
shopify theme check --category=liquid

# Performance checks
shopify theme check --category=performance
```

## Important Files

### Configuration
- `config/settings_schema.json`: Theme customization settings
- `config/settings_data.json`: Current theme setting values

### Core Templates
- `layout/theme.liquid`: Main page layout and HTML structure
- `sections/header.liquid`: Site header with navigation
- `sections/footer.liquid`: Site footer
- `templates/product.json`: Product page template configuration

### Key JavaScript Modules
- `assets/global.js`: Core theme functionality and utilities
- `assets/pubsub.js`: Event system for component communication
- `assets/product-form.js`: Product variant selection and cart functionality
- `assets/cart-drawer.js`: Shopping cart drawer functionality

### Important Snippets
- `snippets/product-variant-picker.liquid`: Product option selection
- `snippets/cart-drawer.liquid`: Cart drawer HTML structure
- `snippets/price.liquid`: Price display with formatting
- `snippets/product-media-gallery.liquid`: Product image/video gallery

## Shopify-Specific Notes

- Always test changes in a development theme before pushing to live
- Be aware of Shopify's Liquid limitations and performance considerations
- Follow Shopify's theme development best practices for code review
- Ensure mobile responsiveness as Shopify stores are heavily mobile-trafficked
- Consider theme performance impact on Core Web Vitals and SEO