# Fdf-project
fdf (file de fer aka wireframe model)
1. Input Handling
   ├── Parse `.fdf` file
   │   ├── Open the file
   │   ├── Read lines
   │   ├── Split into integers
   │   ├── Store in 2D array
   │   └── Handle errors (invalid file, irregular grids, etc.)
   └── Map metadata
       ├── Number of rows (Y-axis)
       └── Number of columns (X-axis)

2. Isometric Transformation
   ├── Convert (X, Y, Z) into isometric coordinates
   │   ├── Apply formulas:
   │       │   x_iso = (x - y) * cos(30°)
   │       │   y_iso = (x + y) * sin(30°) - z
   │   ├── Normalize coordinates to fit in the window
   │   └── Handle scaling for zoom effects
   └── Store projected points

3. Rendering
   ├── Initialize MiniLibX
   │   ├── Create a window
   │   ├── Define colors and line styles
   │   └── Implement zoom/rotation handlers
   ├── Draw lines
   │   ├── Implement Bresenham's line algorithm
   │   └── Handle edge cases (out-of-bounds or overlaps)
   └── Render the wireframe
       ├── Loop through grid points
       │   ├── Draw horizontal edges
       │   └── Draw vertical edges
       └── Optional: Add colors based on altitude

4. Interactivity (Optional)
   ├── Keyboard input
   │   ├── Rotate landscape
   │   ├── Zoom in/out
   │   ├── Adjust position
   │   └── Close the window
   └── Mouse input (optional)
       ├── Drag to rotate
       └── Scroll for zoom

5. Compilation
   ├── `Makefile`
   │   ├── Compile sources
   │   ├── Link MiniLibX and dependencies
   │   └── Include rules for clean/rebuild
   └── Handle dynamic linking for portability
