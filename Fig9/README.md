## Mathematica:
This includes some motor's dimensions plus measurements data.

```Mathematica
r = 0.003

f = If[f0 > 0, f0, 0]

T = f*r*Sin[\[Theta]]

Tavg = Integrate[T, {\[Theta], 0, Pi}]/Pi*20

Tmes = -0.065 + 0.141 Log[p]

MaTeX`

plot = Plot[
  {Tavg, Tmes},
  {p, 1.5, 4},
  PlotRange -> {0, 0.3},
  PlotLabels -> Placed[MaTeX[{"Caclulated", "Measured"}], Above],
  Frame -> True,
  FrameLabel ->MaTeX[{"Pressure \, (Bar)", "Holding \, Torque \, (N.m)"}],
  AspectRatio -> 0.5,
  Filling -> {1 -> Axis, 2 -> Axis},
  BaseStyle -> {FontFamily -> "Times", FontSize -> 10}]

data = {
  {1.69`, 0.0097119`},
  {1.85`, 0.0232497`},
  {2.01`, 0.0315882`},
  {2.17`, 0.0444393`},
  {2.33`, 0.0544455`},
  {2.49`, 0.0658251`},
  {2.65`, 0.0717111`},
  {2.81`, 0.0764199`},
  {3.14`, 0.0993753`},
  {3.61`, 0.116739`}}

plot2 = ListPlot[data, PlotStyle -> {PointSize[0.015], Darker[Orange]}]

myplot = Show[plot, plot2]
```
