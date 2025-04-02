# Light sources
1. Point source
2. Distributed light source
# Light reflection
1. Diffuse reflection
	A ray is scattered at many angles. Lambertian reflection
2. Specular reflection
	mirror like reflection.
# Illumination models
# Basic Illumination Models in Computer Graphics

Illumination models in computer graphics determine how light interacts with surfaces to create realistic images. These models help simulate the effects of light sources, surface materials, and viewing angles. The basic illumination models include:

---

## 1. Ambient Illumination Model

### **Concept:**  
- Simulates indirect lighting by providing a uniform light source.
- Does not consider light direction, reflections, or shadows.
- Helps prevent completely dark areas in a scene.

### **Mathematical Representation:** $$ I = k_a I_a$$
where:  
- \( I \) = ambient light intensity at a point  
- \( k_a \) = ambient reflection coefficient (material property)  
- \( I_a \) = intensity of ambient light source  

### **Pros & Cons:**
✔️ Simple and computationally efficient.  
❌ Does not provide realistic shading or shadows.

---

## 2. Diffuse Illumination Model (Lambertian Reflection)

### **Concept:**  
- Simulates how rough surfaces scatter light evenly in all directions.
- Based on **Lambert’s Cosine Law**, which states that brightness depends on the angle between the light source and surface normal.
- Produces a matte appearance.

### **Mathematical Representation:** $$I_{diff} = k_d I_l (N ⋅ L) $$where:  
- \( I \) = diffuse light intensity  
- \( k_d \) = diffuse reflection coefficient (material property)  
- \( I_l \) = intensity of the light source  
- \( N \) = surface normal vector  
- \( L \) = normalized vector to the light source  

### **Pros & Cons:**
✔️ Simple and effective for matte surfaces.  
❌ Does not account for highlights or reflections.

---

## 3. Specular Illumination Model (Phong Reflection)

### **Concept:**  
- Simulates the appearance of shiny or reflective surfaces.
- Produces **specular highlights**, which depend on the viewer's position.
- The reflection is strongest when the viewing direction aligns with the reflected light direction.

### **Mathematical Representation (Phong Model):**  $$
I = k_s I_l (R ⋅ V)^n
$$
where:  
- \( I \) = specular light intensity  
- \( k_s \) = specular reflection coefficient (material property)  
- \( I_l \) = intensity of the light source  
- \( R \) = reflected light direction  
- \( V \) = view direction  
- \( n \) = shininess exponent (higher values create smaller, sharper highlights)  

### **Pros & Cons:**
✔️ Captures highlights and glossiness.  
❌ Computationally expensive for real-time rendering.

# Shading
1. Flat Shading
	- A simple shading technique where a single color is assigned to an entire polygon.
	- The shading is based on the normal of the polygon and the light source direction.
	
| Feature              | Gouraud Shading                           | Phong Shading                             | Fast Phong Shading                      |
| -------------------- | ----------------------------------------- | ----------------------------------------- | --------------------------------------- |
| Lighting Calculation | Per vertex                                | Per pixel                                 | Approximate per pixel                   |
| Interpolation        | Interpolates vertex colors                | Interpolates vertex normals               | Interpolates vertex normals (optimized) |
| Specular Highlights  | Can be missed or poorly represented       | Accurate and smooth                       | Accurate, but with approximations       |
| Performance          | Very fast (least computational effort)    | Slower (high computational effort)        | Faster than Phong, slower than Gouraud  |
| Quality              | Lower (blocky in low-resolution meshes)   | High-quality, smooth transitions          | Near Phong quality, good balance        |
| Use Cases            | Legacy systems, low-polygon models        | High-quality rendering (CGI, simulations) | Real-time rendering (games, AR/VR)      |
| Advantages           | Simple, efficient, and hardware-friendly  | Produces realistic and smooth lighting    | Good balance of speed and quality       |
| Disadvantages        | Misses highlights; poor for shiny objects | Computationally expensive                 | Slightly less accurate than full Phong  |
Flat Shading
$$Ia = ((ya - y2) / (y1 - y2)) * I1 + ((y1 - ya) / (y1 - y2)) * I2$$
 Gouraud Shading
	
$$


I_a = \frac{y_a - y_2}{y_1 - y_2} I_1 + \frac{y_1 - y_a}{y_1 - y_2} I_2

$$
$$
I_b = \frac{y_a - y_2}{y_3 - y_2} I_3 + \frac{y_3 - y_a}{y_3 - y_2} I_2
$$$$
	I_p = \frac{x_p - x_a}{x_b - x_a} I_b + \frac{x_b - x_p}{x_b - x_a} I_a
	$$

Phong shadinig

$$


N = \frac{y_a - y_2}{y_1 - y_2} N_1 + \frac{y_1 - y_a}{y_1 - y_2} N_2

$$
 Fast- phong shading

$$
	N_{k}=Ax_k+By_k+C,    k=1,2,3...
$$
$$


I_{diff} =\frac{L.N}{|L|.|N|}= \frac{L.N}{|L|.|Ax+By+C|}=\frac{L.(Ax+By+C)}{|L.|.|Ax+By+C|}

$$


Numerical:
![[250402_16h40m23s_screenshot.png]]![[250402_16h40m45s_screenshot.png]]![[250402_16h41m06s_screenshot.png]]






