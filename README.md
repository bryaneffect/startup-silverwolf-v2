# Startup Silverwolf v.2

A reworked personal startup page and project portfolio showcasing design, editing, and development work. Built with HTML, CSS, and JavaScript, with a custom WebGL background shader and interactive motion effects.

## Overview

Startup Silverwolf v.2 is a personal landing page for bryaneffect.int. It combines a portfolio layout, profile cards, and project directory into a single experience. The design uses custom purple styling, animated panels, and a dark/light theme system to create a modern studio-like interface.

## Features

- Custom animated background shader
- Dark and light mode toggle
- Responsive layout for desktop and mobile
- Hover-based project previews with cursor tracking
- Project showcase and directory page
- Profile cards for Silverwolf and Bryan Effect personas
- Social media navigation with animated reveal
- 3D panel transitions and layered card effects
- Copy-to-clipboard terminal panel for project links

## Project Structure

```
startup-silverwolf-v2/
├── index.html
├── projects.html
├── style.css
├── shader-bg.js
├── silverwolficon.png
├── silverwolf.jpg
└── README.md
```

## Pages

### index.html

This is the main startup page and homepage of the site. It includes:

- menu navigation overlay
- profile and personality cards
- social media links
- theme switcher
- footer and identity details

### projects.html

This page acts as the project directory and selected works showcase. It includes:

- project cards and links
- floating preview panel on hover
- project transparency and presentation layout
- terminal-style copy interface for copying project URLs

## Styling

The project uses CSS variables to support theme switching and maintain consistent visual language. The design follows a purple, neon, and minimal studio aesthetic with layered glass-like surfaces and strong contrast.

Main style structure includes:

- global color palette variables
- dark and light mode declarations
- card, menu, and panel layouts
- hover and motion animations
- terminal and badge components

## JavaScript Functionality

The site uses JavaScript for:

- theme persistence with localStorage
- interactive menu toggling
- scroll lock when overlays are opened
- animated preview behavior for showcase items
- clipboard copy support for the project link selector
- WebGL shader rendering for the background animation

## Shader Background

The shader background is implemented in shader-bg.js. It creates a layered noise and color-field effect using WebGL. The script includes:

- canvas-based rendering
- adaptive resizing for performance
- color palette switching for light and dark themes
- optional pointer interaction behavior
- animation timing and visibility checks

## Usage

To use or preview the project locally:

1. Download or clone the repository
2. Open `index.html` in a browser
3. Optionally serve the folder with a local web server if preferred

No build step is required.

## Deployment

This project is intended for static hosting and is compatible with deployment platforms such as Vercel or GitHub Pages.

## Notes

This repository is a personal portfolio and design experiment. It emphasizes visual identity, personal branding, and an interactive web experience rather than a framework-based application.

## Credits

Built for bryaneffect.int.
