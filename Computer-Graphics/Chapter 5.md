# Visible Surface Determination
1. Object space Method
	Deals with object definition to determine which surface as a whole should be visible
2. Image-Space method
	It deals with projected Images
## Back face detection
If an inside point of a polygon is along the line of sight to the surface the polygon must be a back face. Identifies if an object is inside the field of view using the z coordinate.
## Z-Buffer method
- Image space method
- Object depth compared by comparing z values for each pixel 
- Z values are calculated during projection for each x,y
- Stores Intensity and depth value for each x,y
- cannot work with transparency
## A-Buffer method
- extension of z-buffer
- each position has depth and intensity fields
- If depth field is positive only, one surface depth is stored
- If negative, multiple surface overlap at that pixel. Intensity field thus points to the information on
	- RGB intensity
	- Opacity
	- Depth
	- Percent of area coverage
	- Surface Identifier
	- Pointer to surface-rendering parameters
## Scan line methods
Image-space method
- Across each scan line depth calculations are done to determine which surface is closest to view plane
- Edge table and polygon table are used
- Active edge list contains all edges in current scan line
- Surface flags weather a position along a scan line is inside or outside the surface.
- 