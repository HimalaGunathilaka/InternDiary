>[!success] Report
> - Fixed a small bug related to the dynamic icon. The icon shows a green dot if the current url is blocked. It wasn't doing that when adding the url. Fixed it.
> - Studied on 3D printing basics


---
# 3D printing
- https://youtu.be/-D9daYrKvkA
#### Steps
1. **Create 3D Model**
	- Design your object using 3D modeling software (e.g., **Blender**, **FreeCAD**, **Tinkercad**).
	- Ensure the model is **watertight/manifold** (no holes or non-manifold edges) so it can be printed properly.
	- Scale your model to the desired physical size.

2.  **Prepare 3D Model for Printing (Slicing)**
    - **Slicing:** The 3D model is divided into **thin layers** to generate **G-code**, a set of instructions that tells the printer how to move, extrude material, and build each layer.
    - **Key slicing settings to consider:**
        - **Layer height:** Determines print resolution (smaller = finer detail).
        - **[Infill](https://help.prusa3d.com/article/infill-patterns_177130):** Internal structure of the model (e.g., 10–100%). Lower infill saves material but reduces strength.
            - Common patterns: **grid, honeycomb, gyroid**
        - **Supports:** Temporary structures for overhangs.
        - **Brim / Raft:** Improves bed adhesion for tricky prints.
        - **Print speed & temperature:** Adjust based on filament type (PLA, ABS, PETG, etc.).
    - Recommended slicers: **Ultimaker Cura, PrusaSlicer, SuperSlicer**

3. **Choose Printer & Material**
	- **Printer type:** Most common is **Fused Filament Fabrication (FFF)** or **Fused Deposition Modeling (FDM)**.
	- **Filament materials:** PLA (easy to print), ABS (stronger, heat resistant), PETG, TPU, etc.
	- ==Filament diameter must match the printer (usually 1.75 mm or 2.85 mm).==

4. **Setup the 3D Printer**
	- **Level the print bed** to ensure proper first layer adhesion.
	- **Calibrate the extruder** to extrude the correct amount of filament.
	- Check printer cleanliness and maintenance (no clogged nozzles, smooth motion)

5. **Load Filament & Start Printing**
	- Load filament and preheat nozzle & bed according to material.
	- Start the print and monitor the first few layers to avoid issues.
	- Ensure proper cooling and layer adhesion during printing.

6. **Post-Processing & Finishing**
	- **Remove support structures** carefully.
	- **Sanding & smoothing** edges or surfaces.
	- **Coating or painting** (optional) for aesthetics or protection.
	- **Assembly:** Glue or fit parts together if printed in multiple pieces.

----
# Shops to consider
- https://3dprinting.rysera.com/