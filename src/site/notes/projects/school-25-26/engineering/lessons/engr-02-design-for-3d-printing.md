---
{"dg-publish":true,"permalink":"/projects/school-25-26/engineering/lessons/engr-02-design-for-3d-printing/"}
---


# Engineering a design for 3D printing

[Source article here](https://blog.rahix.de/design-for-3d-printing/)
[[projects/school-25-26/engineering/design-for-3d-printing\|Local copy of article, because it's that good]]


1. **Designing for Part Strength**
    -  [**R1.1**](https://blog.rahix.de/design-for-3d-printing/#rule-R1.1) — Tensile forces should be aligned parallel to the print surface.
    -  [**R1.2**](https://blog.rahix.de/design-for-3d-printing/#rule-R1.2) — Split a part into multiple pieces when no orientation is ideal for all loads.
    -  [**R1.3**](https://blog.rahix.de/design-for-3d-printing/#rule-R1.3) — Most strength comes from the part's surface, not the infill.
    -  [**R1.4**](https://blog.rahix.de/design-for-3d-printing/#rule-R1.4) — Guide forces on the most direct path possible.
    -  [**R1.5**](https://blog.rahix.de/design-for-3d-printing/#rule-R1.5) — Use large cross sections. Prefer thick shapes over thin shapes.
2. **Manufacturing Tolerance and Part Finish**
    -  [**R2.1**](https://blog.rahix.de/design-for-3d-printing/#rule-R2.1) — Use chamfers on edges parallel to the print surface. Use fillets on edges vertical to the print surface.
    -  [**R2.2**](https://blog.rahix.de/design-for-3d-printing/#rule-R2.2) — Improve horizontal holes by using a teardrop shape or giving the hole a flat roof.
    -  [**R2.3**](https://blog.rahix.de/design-for-3d-printing/#rule-R2.3) — Use a teardrop shape for vertical holes to avoid inaccuracy due to perimeter seams.
    -  [**R2.4**](https://blog.rahix.de/design-for-3d-printing/#rule-R2.4) — Consider where the seam will be placed. If tolerances are tight, provide a sharp concave corner for the seam the hide in.
    -  [**R2.5**](https://blog.rahix.de/design-for-3d-printing/#rule-R2.5) — Design part geometry for easy motion paths while printing, to improve dimensional accuracy.
    -  [**R2.6**](https://blog.rahix.de/design-for-3d-printing/#rule-R2.6) — Prevent warping by making parts voluminous and their surfaces smooth and rounded. The ideal shape is a sphere.
    -  [**R2.7**](https://blog.rahix.de/design-for-3d-printing/#rule-R2.7) — If you can't make it precise, make it adjustable.
    -  [**R2.8**](https://blog.rahix.de/design-for-3d-printing/#rule-R2.8) — Do not use circular holes for interference fits. Use hexagon or square holes instead.
    -  [**R2.9**](https://blog.rahix.de/design-for-3d-printing/#rule-R2.9) — Use crush ribs for press fits that are only assembled once.
    -  [**R2.10**](https://blog.rahix.de/design-for-3d-printing/#rule-R2.10) — Use grip fins for press fits that need to be reassembled more than once.
3. **Process Optimization**
    -  [**R3.1**](https://blog.rahix.de/design-for-3d-printing/#rule-R3.1) — Avoid the necessity of support material.
    -  [**R3.2**](https://blog.rahix.de/design-for-3d-printing/#rule-R3.2) — Clever part orientation on the print surface can eliminate the need for supports.
    -  [**R3.3**](https://blog.rahix.de/design-for-3d-printing/#rule-R3.3) — Split a part into multiple pieces when no orientation can avoid supports.
    -  [**R3.4**](https://blog.rahix.de/design-for-3d-printing/#rule-R3.4) — Use sacrificial layers to avoid internal overhangs that would otherwise require supports.
    -  [**R3.5**](https://blog.rahix.de/design-for-3d-printing/#rule-R3.5) — Use the overhanging counterbore trick.
    -  [**R3.6**](https://blog.rahix.de/design-for-3d-printing/#rule-R3.6) — Bridges on top of other bridges allow for advanced geometry, without requiring additional support structure.
    -  [**R3.7**](https://blog.rahix.de/design-for-3d-printing/#rule-R3.7) — Keep surface area minimal. Design voluminous. Do not make cutouts in an attempt to save material.
    -  [**R3.8**](https://blog.rahix.de/design-for-3d-printing/#rule-R3.8) — Reduce the surface area that is touching the print-bed when aiming for mass production.
    -  [**R3.9**](https://blog.rahix.de/design-for-3d-printing/#rule-R3.9) — Add mouse ears to parts that have problems with bed adhesion.
4. **Functional Integration**
    -  [**R4.1**](https://blog.rahix.de/design-for-3d-printing/#rule-R4.1) — Use zip tie channels to fasten cables to a part.
    -  [**R4.2**](https://blog.rahix.de/design-for-3d-printing/#rule-R4.2) — Use flexures to integrate moving features into a part.
    -  [**R4.3**](https://blog.rahix.de/design-for-3d-printing/#rule-R4.3) — Design flexures such that they only deform elastically when used.
    -  [**R4.4**](https://blog.rahix.de/design-for-3d-printing/#rule-R4.4) — Ensure that flexures have hard limits that prevent breaking them.
    -  [**R4.5**](https://blog.rahix.de/design-for-3d-printing/#rule-R4.5) — Ensure clips won't break from use. Optimize designs for minimal clip movement.
    -  [**R4.6**](https://blog.rahix.de/design-for-3d-printing/#rule-R4.6) — Provide a way to undo form-locking clips.
    -  [**R4.7**](https://blog.rahix.de/design-for-3d-printing/#rule-R4.7) — Use break-away surfaces to support floating geometry in print-in-place designs.
    -  [**R4.8**](https://blog.rahix.de/design-for-3d-printing/#rule-R4.8) — Ensure sufficient clearance between features in print-in-place designs.
5. **Beyond plastic - Machine Elements**
    -  [**R5.1**](https://blog.rahix.de/design-for-3d-printing/#rule-R5.1) — Protect dynamically loaded screws with additional locking measures like threadlocking adhesive.
    -  [**R5.2**](https://blog.rahix.de/design-for-3d-printing/#rule-R5.2) — Design screwed connections for maximum screw length.
    -  [**R5.3**](https://blog.rahix.de/design-for-3d-printing/#rule-R5.3) — Cut threads into printed parts with a thread tap for quick design of low-reuse joints.
    -  [**R5.4**](https://blog.rahix.de/design-for-3d-printing/#rule-R5.4) — Use rib thread forming for no-postprocessing low-reuse threads in printed parts.
    -  [**R5.5**](https://blog.rahix.de/design-for-3d-printing/#rule-R5.5) — Use heat-set threaded inserts to add highly reusable and robust threads to a part.
    -  [**R5.6**](https://blog.rahix.de/design-for-3d-printing/#rule-R5.6) — Make cutouts to embed standard nuts into a part.
    -  [**R5.7**](https://blog.rahix.de/design-for-3d-printing/#rule-R5.7) — Embed hardware into 3d-printed parts to avoid more complex fastening or joining methods.
6. **Appearance**
    -  [**R6.1**](https://blog.rahix.de/design-for-3d-printing/#rule-R6.1) — Complex shapes are often "for free" in 3d-printing. Use them to improve appearance or ergonomics.
    -  [**R6.2**](https://blog.rahix.de/design-for-3d-printing/#rule-R6.2) — Create shadow lines along the joining edge between two parts.
    -  [**R6.3**](https://blog.rahix.de/design-for-3d-printing/#rule-R6.3) — Use surface texture to make parts appear less 3d-printed.
    -  [**R6.4**](https://blog.rahix.de/design-for-3d-printing/#rule-R6.4) — Prefer engraving text over embossing.
    -  [**R6.5**](https://blog.rahix.de/design-for-3d-printing/#rule-R6.5) — Place engraved/embossed text vertical to the print surface.
7. **Extra: Vase Mode Design**
    -  [**R7.1**](https://blog.rahix.de/design-for-3d-printing/#rule-R7.1) — Use beading patterns to make vase mode parts more stiff.