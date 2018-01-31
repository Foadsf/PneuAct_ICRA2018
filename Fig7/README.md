## Description:
This figure present the results of the experiment described in Figure 5., plotting an interpolated graphs of forces generated in a cylinder piston with different nominal

`Fig7_1.csv` is the force measurements (N) for cylinder-pistons with different clearances (first Row mm) at different input pressures (First column Bar). It should be noted that the clearances are nominal values based on the original CAD files not the actual measurements. the difference between the clearances does not necessarily represent the resolutions of the #D printing machine Fortus 250.

`Fig7_2.csv` includes the minimum required pressure (third row Bar) to overcome the static friction and the residual forces (second row N) measured in the pressure sensor after depressurization for different clearances (first row mm).

`Fig7_3.csv` includes the actual dimensions of the cylinders measured with a clipper. First column (`ideal gap`) is the ideal clearance in mm. second column is the ideal length of the cylinders in mm. Third column (`xy length`) is the measured length of the cylinder for the side printed horizontally. Column 4 (`z length`) is the measured length of the cylinder for the side printed vertically. As can be seen the 3D printer has a lower precision in z direction.

```Mathematica
press[x_, fo_] = (fo +(18.369*Exp[-2.491*x]))/(29.512*Exp[-9.691*x])

fs[x_] = (7.14286/x + 51.0204 Log[7. - 50. x] - 51.0204 Log[x])/10

plot = cleanContourPlot[
  ContourPlot[press[x, fo], {x, 0.05, 0.35}, {fo, 0, 80},
   PlotRange -> {2, 8},
   RegionFunction ->
    Function[{x, fo, press}, If[x < 0.14, fs[x] < fo, 0 < fo]],
   BoundaryStyle -> Black,
   Contours -> {2, 2.5, 3, 3.5, 4, 4.5, 5, 5.5, 6, 6.5, 7, 7.5, 8},  
   FrameLabel ->
    MaTeX[{" Clearance \, (mm)\, stick-slip", "Force \, (N)"}],
   PlotLegends ->
    Placed[BarLegend[Automatic, LegendMarkerSize -> 250,
      LegendFunction -> (Framed[#, RoundingRadius -> 5] &),
      LegendMargins -> 3, LegendLabel -> MaTeX["Pressure \, (Bar)"],
      BaseStyle -> {FontFamily -> "Times", FontSize -> 10}], {After,
      Top}], LabelStyle -> Directive[Black, Bold, Medium],
   AspectRatio -> Full,
   BaseStyle -> {FontFamily -> "Times", FontSize -> 10}]]
```
