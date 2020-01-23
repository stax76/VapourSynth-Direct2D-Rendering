
# VapourSynth Direct2D Rendering

C++ classic WinAPI sample application that renders a VapourSynth script using Direct2D.

Script must do FlipVertical and use format COMPATBGR32, I don't know how to do this using the VapourSynth API.

```Python
clip = core.std.FlipVertical(clip)

if clip.format.id == vs.RGB24:
    _matrix_in_s = 'rgb'
else:
    if clip.height > 576:
        _matrix_in_s = '709'
    else:
        _matrix_in_s = '470bg'

clip = clip.resize.Bicubic(matrix_in_s = _matrix_in_s, format = vs.COMPATBGR32)
clip.set_output()
```
