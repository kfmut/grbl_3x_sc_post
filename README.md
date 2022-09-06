# grbl_3x_sc_post

GRBL 3-axis mill/router post processor for Stable Design SheetCam

## Notes

Post processor is tested with SheetCam TNG V6.0.30
**G28 safe postion is ON\
Tool change M6 commands is ON\
Line numbering is ON**

Always check generated G-code before sending it to your mill/router!

BEWARE: first toolchange position is explicitly specified at SafeZ height

## Output Code Example

```
N00001 G17
N00002 G21
N00003 G94
N00004 G28 G91 Z0
N00005 G90

N00006 G0 X0.000 Y0.000
N00007  Z6.000
N00008 ( MSG, 2.5*10mm 1/8inSHNK 6F KUKURUZA )
N00009 T384 M6

N00010 G0 Z6.000
N00011 M3 S6000
N00012 G0 X-2.275 Y0.214
N00013  Z2.000
N00014 G1 Z0.750 F50
N00015 G2 X2.233 Y0.600 I2.448 J-2.061 F720
N00016 G3 X3.876 Y0.001 I1.643 J1.951
N00017 G1 X97.980
N00018 G3 X100.464 Y1.972 I0.000 J2.550
N00019 G1 X102.900 Y12.432
...
N00380 G2 X3.135 Y-3.297 I-2.061 J-2.448
N00381 G0 Z6.000
N00382 M5

N00383 G28 G91 Z0
N00384 G28 G91 X0 Y0
N00385 M30
```
