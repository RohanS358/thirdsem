# Use of computer Graphics
1. UI
2. Data Visualization
3. Office autoamtion and electronic publishing
4. CAD and drafting
5. Scientific/business visualization
6. Simulation and VR
7. Entertainment
8. Art and Commerce
9. Civil engineering
10. Medical application
11. Internet
# General terms
1. Pixel
2. Aliasing
3. Anti aliasing
4. Pixel phasing
5. Interlacing
6. Bit depth
7. Florescence and phosphorescence
8. Persistence
9. Refresh rate
10. Horizontal Scan rate
11. Resolution
	factors affecting resolution
	1. spot profile
	2. iintensit2ies
12. Horizontal and vertical retrace
13. bit map=pix map= frame buffer
# hardware Concepts
### tablet
1. Electrical
2. sonic
3. Resistive
### touch panel
1. Optical
2. Electrical
3. Sonic
### Light pen
### Keyboard

### Mouse
1. Mechanical
2. Optical
### Barcode reader

### Data Glove

# Random Scan display and Vector Scan Display
# Difference between Raster Scan Display and Random (Vector) Scan Display

| Base of Difference     | Raster Scan Display                                                                                                                        | Random (Vector) Scan Display                                                           |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------- |
| **Electron beam**      | The electron beam is swept across the screen one row at a time from top to bottom.                                                         | The electron beam is swept to the parts of the screen where a picture is to be drawn.  |
| **Resolution**         | It has lower or poor resolution because picture definition is stored as an intensity value.                                                | It has high resolution because it stores picture definition as a set of line commands. |
| **Picture definition** | Picture definition is stored as a set of intensity values for all screen points (pixels) in a refresh buffer.                              | Picture definition is stored as a set of lines in a display list file.                 |
| **Realistic display**  | The capacity of the system to store intensity values for pixels makes it well suited for realistic display with shadow and color patterns. | These systems are designed for line drawing and can't display realistic shaded scenes. |
| **Image drawing**      | Screen points or pixels are used to draw an image.                                                                                         | Mathematical functions are used to draw an image.                                      |
| **Cost**               | They are cheaper than random display.                                                                                                      | It is more expensive than raster scan display.                                         |
| **Refresh rate**       | Refresh rate is 60-80 fps.                                                                                                                 | All components are drawn 30 to 60 times per second.                                    |
| **Interlacing**        | It uses interlacing.                                                                                                                       | It doesn't use interlacing.                                                            |
| **Editing**            | Editing is difficult.                                                                                                                      | Editing is easy.                                                                       |
| **Refresh area**       | Refresh area is independent of picture complexity.                                                                                         | Refresh area depends on complexity of picture.                                         |
| **Smoothness**         | Produces jagged lines.                                                                                                                     | Produces smooth lines.                                                                 |
| **Example**            | CRT, TV, Printer                                                                                                                           | Pen Plotter                                                                            |
# Color CRT monitors
1. Beam penetration
2. Shadow mask
	1. Delta Delta
	2. Precision Inline
# Display system Architecture
![[250319_09h18m41s_screenshot.png]]
![[250319_09h18m41s_screenshot.png]]
![[250319_09h19m11s_screenshot.png]]
# Flat Panel Displays
1. Emissive
	1. Plasma Panel
	2. Thin film Electroluminescent Display
	3. LED
2. Non emissive
	LCD
# Questions
1. Differentiate between raster and vector scan display
2. Write a short note on beam penetration CRT, shadow mask CRT, delta delta CRT, precision inline CRT
3. Write a short note on Raster scan Display architecture, Random Scan display architecture
4. What is a video controller
5. What are flat panel displays? Differentiate between emissive and non emissive displays?
6. Write about the major parts OF CRT
## Numericals
![[250319_08h55m16s_screenshot.png]]


## **1. 2D Viewing Pipeline**

The **2D viewing pipeline** transforms a 2D scene from world coordinates to device coordinates (such as a monitor or printer). It consists of the following steps:

### **Steps in the 2D Viewing Pipeline**

1. **World Coordinate System (WCS) Definition**
    
    - The user defines objects in world coordinates.
        
2. **Windowing (Selection of Viewing Region)**
    
    - A **window** (a rectangular region in world space) is chosen to define what part of the scene should be displayed.
        
3. **Transform to Normalized Device Coordinates (NDC)**
    
    - The window is mapped to a normalized coordinate system, typically ranging from **(0,0) to (1,1)**.
        
4. **Viewport Transformation**
    
    - The normalized coordinates are scaled and mapped to the viewport, which represents the actual screen display area.
        
5. **Clipping**
    
    - Objects or parts of objects outside the window are clipped using clipping algorithms (e.g., **Cohen-Sutherland, Liang-Barsky**).
        
6. **Device Coordinates and Display**
    
    - The final transformed coordinates are mapped onto the output device, such as a monitor.
## **2. 3D Viewing Pipeline**

The **3D viewing pipeline** extends the 2D pipeline by adding depth and perspective transformations. It is used in 3D graphics applications such as gaming, simulations, and CAD.

### **Steps in the 3D Viewing Pipeline**

1. **Modeling Coordinates (Object Space)**
    
    - Objects are defined in their own local coordinate system.
        
2. **World Coordinate System (WCS) Transformation**
    
    - The objects are positioned in a common 3D world coordinate system.
        
3. **Viewing Transformation (Camera Setup)**
    
    - A virtual camera (view reference coordinate system) is set up.
        
    - **View Volume** (a 3D equivalent of a 2D window) is defined.
        
4. **Projection Transformation**
    
    - The 3D scene is projected onto a 2D plane.
        
    - **Orthographic Projection:** No perspective (parallel projection).
        
    - **Perspective Projection:** Objects farther away appear smaller.
        
5. **Clipping (3D Clipping Algorithms)**
    
    - Objects outside the viewing volume are clipped.
        
6. **Viewport Mapping (Normalization & Device Coordinates)**
    
	    - The final 2D image is mapped onto the viewport for display.