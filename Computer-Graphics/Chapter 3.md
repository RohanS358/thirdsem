# transformations
do the below numericals4
![[250322_12h27m58s_screenshot 1.png]]
![[250322_12h27m26s_screenshot 1.png]]
![[250322_12h29m16s_screenshot 1.png]]![[250322_12h29m34s_screenshot 1.png]]
![[250322_12h30m06s_screenshot 1.png]]


# Perspective and Parallel Projection  

Projection is used in computer graphics to map **3D objects** onto a **2D plane** (such as a screen). The two main types are **Perspective Projection** and **Parallel Projection**.  

---

## 1. Perspective Projection  
Perspective projection simulates **real-world depth perception**, making distant objects appear **smaller** while closer objects appear **larger**.  

### **Characteristics**  
- ✅ Objects farther away appear smaller.  
- ✅ Parallel lines may converge at a **vanishing point**.  
- ✅ Creates a realistic sense of **depth**.  
- ✅ Used in **video games, 3D modeling, VR, and movies**.  

### **Types of Perspective Projection**  
1. **One-Point Perspective** → Lines converge at a single vanishing point.  
2. **Two-Point Perspective** → Two vanishing points are used (common in architecture).  
3. **Three-Point Perspective** → Three vanishing points for extreme depth effects.  

### **Mathematical Formula**  
\[
X' = \frac{X}{Z}, \quad Y' = \frac{Y}{Z}
\]  
where **(X, Y, Z)** is the original 3D coordinate, and **(X', Y')** is the projected 2D coordinate. The division by **Z** creates the depth effect.  

---

## 2. Parallel Projection  
Parallel projection is used when **depth perception is not needed**. Unlike perspective projection, **parallel lines remain parallel**, and object sizes do not change with distance.  

### **Characteristics**  
- ✅ No depth effect.  
- ✅ Parallel lines remain **parallel**.  
- ✅ Used in **engineering, CAD, and technical drawings**.  
- ✅ No vanishing points.  

### **Types of Parallel Projection**  
1. **Orthographic Projection** → Used in **blueprints, CAD, and technical drawings**.  
   - **Common Views**:  
     - Front View  
     - Top View  
     - Side View  
2. **Oblique Projection** → Objects are projected at an **angle**, allowing some depth to be seen.  
   - **Cavalier Projection** → Full depth preserved.  
   - **Cabinet Projection** → Half-depth for realism.  
3. **Isometric Projection** → Special **axonometric** projection where angles between axes are **120°**.  
   - Used in **isometric games, pixel art, and technical drawings**.  

### **Mathematical Formula**  
For **orthographic projection**:  
\[
X' = X, \quad Y' = Y
\]  
Here, the **Z-coordinate is ignored**.  

---

## **Comparison Table**
| Feature              | Perspective Projection        | Parallel Projection |
| -------------------- | ----------------------------- | ------------------- |
| **Depth Perception** | ✅ Realistic                   | ❌ No depth effect   |
| **Parallel Lines**   | ❌ Converge at vanishing point | ✅ Stay parallel     |
| **Applications**     | 🎮 Games, VR, Movies          | 📐 CAD, Engineering |
| **Complexity**       | 🔴 More complex               | 🟢 Simple           |
| **Realism**          | 🌟 High                       | 📏 Low              |

---

## **Conclusion**
Both **perspective** and **parallel projection** are useful in different scenarios:  
- **Perspective Projection** is ideal for **realistic** applications like **games and VR**.  
- **Parallel Projection** is used where **precise measurements** are needed, such as in **engineering and CAD**.  

---

Would you like **code examples in C++/OpenGL**? 🚀  
# **Composite Transformations in 2D and 3D Using Matrices**

Composite transformations involve **combining multiple transformations** (such as translation, scaling, and rotation) into a **single matrix** to be applied in one step. This is more efficient than applying transformations separately.

---

## **1. 2D Composite Transformations**

In **2D graphics**, transformations are represented using **3×3 matrices**. This allows us to perform translation along with other transformations using **homogeneous coordinates**.

### **Basic 2D Transformation Matrices**

1. **Translation** (moving an object)
    
    T=[10tx01ty001]T = \begin{bmatrix} 1 & 0 & t_x \\ 0 & 1 & t_y \\ 0 & 0 & 1 \end{bmatrix}
    - Moves a point **(x, y)** by txt_x and tyt_y.
2. **Scaling** (resizing an object)
    
    S=[sx000sy0001]S = \begin{bmatrix} s_x & 0 & 0 \\ 0 & s_y & 0 \\ 0 & 0 & 1 \end{bmatrix}
    - Scales a point by **sxs_x** in the x-direction and **sys_y** in the y-direction.
3. **Rotation** (rotating an object counterclockwise by an angle θ\theta)
    
    R=[cos⁡θ−sin⁡θ0sin⁡θcos⁡θ0001]R = \begin{bmatrix} \cos \theta & -\sin \theta & 0 \\ \sin \theta & \cos \theta & 0 \\ 0 & 0 & 1 \end{bmatrix}
    - Rotates a point around the origin by **θ\theta degrees**.

---

### **Composite 2D Transformation**

To apply multiple transformations, we **multiply** their matrices together in the correct order.

For example, to:

1. Scale an object
2. Then rotate it
3. Then translate it

The **composite transformation matrix** is:

C=T⋅R⋅SC = T \cdot R \cdot S

To transform a **point (x,y)(x, y)**, we multiply it by the **composite matrix**:

P′=C⋅PP' = C \cdot P

### **Order of Operations in 2D**

- **Scaling before translation** → Object scales from the origin.
- **Translation before scaling** → Object scales from its current position.
- **Rotation before translation** → Object rotates about the origin before moving.

---

## **2. 3D Composite Transformations**

In **3D graphics**, transformations use **4×4 matrices** to handle translations properly using **homogeneous coordinates**.

### **Basic 3D Transformation Matrices**

1. **Translation**
    
    T=[100tx010ty001tz0001]T = \begin{bmatrix} 1 & 0 & 0 & t_x \\ 0 & 1 & 0 & t_y \\ 0 & 0 & 1 & t_z \\ 0 & 0 & 0 & 1 \end{bmatrix}
2. **Scaling**
    
    S=[sx0000sy0000sz00001]S = \begin{bmatrix} s_x & 0 & 0 & 0 \\ 0 & s_y & 0 & 0 \\ 0 & 0 & s_z & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix}
3. **Rotation about the X-axis**
    
    Rx=[10000cos⁡θ−sin⁡θ00sin⁡θcos⁡θ00001]R_x = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & \cos \theta & -\sin \theta & 0 \\ 0 & \sin \theta & \cos \theta & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix}
4. **Rotation about the Y-axis**
    
    Ry=[cos⁡θ0sin⁡θ00100−sin⁡θ0cos⁡θ00001]R_y = \begin{bmatrix} \cos \theta & 0 & \sin \theta & 0 \\ 0 & 1 & 0 & 0 \\ -\sin \theta & 0 & \cos \theta & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix}
5. **Rotation about the Z-axis**
    
    Rz=[cos⁡θ−sin⁡θ00sin⁡θcos⁡θ0000100001]R_z = \begin{bmatrix} \cos \theta & -\sin \theta & 0 & 0 \\ \sin \theta & \cos \theta & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix}

---

### **Composite 3D Transformation**

To apply multiple transformations, multiply their matrices together.

For example, to:

1. Rotate an object around the **Z-axis**
2. Then scale it
3. Then translate it

The **composite transformation matrix** is:

C=T⋅S⋅RzC = T \cdot S \cdot R_z

To transform a **3D point (x,y,z)(x, y, z)**, we multiply it by **C**:

P′=C⋅PP' = C \cdot P

### **Order of Operations in 3D**

- **Scaling before rotation** → Object scales before it rotates.
- **Rotation before translation** → Object rotates around the **origin**, then moves.
- **Translation before rotation** → Object moves first, then rotates around its new position.

---

## **Key Takeaways**

✅ **Matrix multiplication is used to combine transformations** for efficiency.  
✅ **The order of multiplication matters**—changing the sequence changes the final position.  
✅ **Homogeneous coordinates allow translations to be represented as matrix operations**.  
✅ **2D transformations use 3×3 matrices**, while **3D transformations use 4×4 matrices**.  
✅ **Composite transformations make multiple operations faster and more efficient**.

# **Composite Transformations in 2D and 3D Using Matrices**  

Composite transformations involve **combining multiple transformations** (such as translation, scaling, and rotation) into a **single matrix** to be applied in one step. This is more efficient than applying transformations separately.

---

## **1. 2D Composite Transformations**  
In **2D graphics**, transformations are represented using **3×3 matrices**. This allows us to perform translation along with other transformations using **homogeneous coordinates**.

### **Basic 2D Transformation Matrices**  
1. **Translation** (moving an object)  
   $$
   T = \begin{bmatrix} 1 & 0 & t_x \\ 0 & 1 & t_y \\ 0 & 0 & 1 \end{bmatrix}
   $$

2. **Scaling** (resizing an object)  
   $$
   S = \begin{bmatrix} s_x & 0 & 0 \\ 0 & s_y & 0 \\ 0 & 0 & 1 \end{bmatrix}
   $$

3. **Rotation** (rotating an object counterclockwise by an angle \( \theta \))  
   $$
   R = \begin{bmatrix} \cos \theta & -\sin \theta & 0 \\ \sin \theta & \cos \theta & 0 \\ 0 & 0 & 1 \end{bmatrix}
   $$

---

### **Composite 2D Transformation**  
To apply multiple transformations, we **multiply** their matrices together in the correct order.  

For example, to:
1. Scale an object  
2. Then rotate it  
3. Then translate it  

The **composite transformation matrix** is:
   $$
   C = T \cdot R \cdot S
   $$

To transform a **point \( (x, y) \)**, we multiply it by the **composite matrix**:
   $$
   P' = C \cdot P
   $$

---

## **2. 3D Composite Transformations**  
In **3D graphics**, transformations use **4×4 matrices** to handle translations properly using **homogeneous coordinates**.

### **Basic 3D Transformation Matrices**  
1. **Translation**  
   $$
   T = \begin{bmatrix} 1 & 0 & 0 & t_x \\ 0 & 1 & 0 & t_y \\ 0 & 0 & 1 & t_z \\ 0 & 0 & 0 & 1 \end{bmatrix}
   $$

2. **Scaling**  
   $$
   S = \begin{bmatrix} s_x & 0 & 0 & 0 \\ 0 & s_y & 0 & 0 \\ 0 & 0 & s_z & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix}
   $$

3. **Rotation about the X-axis**  
   $$
   R_x = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & \cos \theta & -\sin \theta & 0 \\ 0 & \sin \theta & \cos \theta & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix}
   $$

4. **Rotation about the Y-axis**  
   $$
   R_y = \begin{bmatrix} \cos \theta & 0 & \sin \theta & 0 \\ 0 & 1 & 0 & 0 \\ -\sin \theta & 0 & \cos \theta & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix}
   $$

5. **Rotation about the Z-axis**  
   $$
   R_z = \begin{bmatrix} \cos \theta & -\sin \theta & 0 & 0 \\ \sin \theta & \cos \theta & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix}
   $$

---

### **Composite 3D Transformation**  
To apply multiple transformations, multiply their matrices together.  

For example, to:
1. Rotate an object around the **Z-axis**  
2. Then scale it  
3. Then translate it  

The **composite transformation matrix** is:
   $$
   C = T \cdot S \cdot R_z
   $$

To transform a **3D point \( (x, y, z) \)**, we multiply it by **C**:
   $$
   P' = C \cdot P
   $$
---
## **2. Projection in 3D Display Modes**

Projections help convert **3D objects into 2D screen coordinates**.

### **(a) Parallel Projection (For Technical Applications)**

- **No perspective distortion** (lines remain parallel).
    
- Used in **CAD software, blueprints, and schematics**.
    

### **(b) Perspective Projection (For Realism)**

- **Objects shrink with distance**, mimicking human vision.
    
- Used in **games, movies, and virtual reality**.

# TODO: ADD PROJECTION NUMERICALS