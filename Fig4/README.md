## Description:
The folder [`MRIimages`](lik/todo) contains the MRI images taken with the `scanner 0.25T G-scan Brio, Esaote SpA (Genoa, Italy)` scanner.

|| No Motor | Motor Off | Motor On |
|-|:-:|:-:|:-:|
|Spin Echo|1_SE_NM.jpg|1_SE_OF.jpg|1_SE_ON.jpg|
|Gradient Echo|1_GE_NM.jpg|1_GE_OF.jpg|1_GE_ON.jpg|

## python:
This python code was used to calculate the Signal to noise ratios:
```python
from PIL import Image
from scipy.stats import signaltonoise
jpgfile = Image.open(r"/path/to/the/MRIimage.jpg")
signaltonoise(jpgfile, axis=None)
```
