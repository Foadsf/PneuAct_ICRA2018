## Description:
The file [`Fig10.csv`](todo/link) contains the Torque measurements at different Stepping frequencies and different input pressures.


## Mathematica:

```Mathematica
plot = cleanContourPlot[
  ContourPlot[
    Exp[((Fo + 0.035*Exp[-0.116*f])/(0.094*Exp[-0.026*f]))],
    {f, 0,100},
    {Fo, 0, 0.15},
    PlotRange -> {0, 7},
    Contours -> {2, 2.5, 3, 3.5, 4, 4.5, 5, 5.5, 6, 6.5, 7},
    BoundaryStyle -> Black,
    PlotLegends -> Placed[
      BarLegend[Automatic,
      LegendMarkerSize -> 150,
      LegendFunction -> (Framed[#, RoundingRadius -> 5] &),
      LegendLabel -> MaTeX["Pressure \, (Bar)"],
      BaseStyle -> {FontFamily -> "Times", FontSize -> 10}],
      {After,Top}],
    FrameLabel -> MaTeX[{"Stepping \, frequency \, (Hz)", "Torque \, (N.m)"}],
    LabelStyle -> Directive[Black, Bold, Medium],
    AspectRatio -> Full,
    BaseStyle -> {FontFamily -> "Times", FontSize -> 10}]]
```
