## Description:
In this figure the empirical model described in Equation .1 has been plotted. The mathematical model described in Equation .1 is driven from measurements using experimental setup described in Figure 5. The data points can be found in the folder [`Fig6_data`](https://github.com/Foadsf/PneuAct_ICRA2018/tree/master/Fig6/Fig6_data). The folder includes `.csv` files with a naming format like `tube_l1_p3_start.csv` which means the pressure measurements for a tube of length `1m` and input pressure `3Bar` for inhale phase. Respectively the file `tube_l1_p3_end.csv` is for the same tube but during the exhale phase.



```Mathematica
fun[t_, r_] = -3.` Log[-((20.` Log[-0.846481724890614` (-1.` + r)])/t)]

plot2 = cleanContourPlot[
  ContourPlot[
    fun[t, r],
    {t, 0, 500},
    {r, 0, 1},
    Contours -> {1, 2, 3, 4, 5, 6, 7, 8},
    PlotRange -> {0.9, 8.5},
    BoundaryStyle -> Black,
    FrameLabel -> MaTeX[{"Time \, (msec)", "P/P_1"}],
    PlotLegends -> Placed[
      BarLegend[
        Automatic,
        LegendMarkerSize -> 250,
        LegendFunction -> (Framed[#, RoundingRadius -> 5] &),
        LegendMargins -> 3,
        LegendLabel -> MaTeX["Length \, (m)"],
        BaseStyle -> {FontFamily -> "Times", FontSize -> 10}],
      {After, Top}],
    LabelStyle -> Directive[Black, Bold, Medium],
    AspectRatio -> Full,
    BaseStyle -> {FontFamily -> "Times", FontSize -> 10}]]
```

