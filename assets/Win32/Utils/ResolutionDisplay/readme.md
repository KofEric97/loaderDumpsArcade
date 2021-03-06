# Resolution Display

```c

######################################
# ENUMS - CONFIG_RESOLUTION
#
# FULLSCREEN_NATIVE
# FULLSCREEN_NATIVE_ROTATION_90
# FULLSCREEN_NATIVE_ROTATION_180
# FULLSCREEN_NATIVE_ROTATION_270
# FULLSCREEN
# FULLSCREEN_ROTATION_90
# FULLSCREEN_ROTATION_180
# FULLSCREEN_ROTATION_270
# WINDOWED_CENTER
# WINDOWED_CENTER_ROTATION_90
# WINDOWED_CENTER_ROTATION_180
# WINDOWED_CENTER_ROTATION_270
# WINDOWED
# WINDOWED_ROTATION_90
# WINDOWED_ROTATION_180
# WINDOWED_ROTATION_270
######################################
RESOLUTION_DISPLAY = WINDOWED

//File with external configuration
std::unique_ptr properties = std::make_ptr<Properties>();
properties->read();

std::unique_ptr resolutionDisplay = std::make_ptr<ResolutionDisplay>();
auto display = properties->getString("RESOLUTION_DISPLAY");
auto value = pResolutionDisplay->toEnum(display.c_str());

switch (value) {
  case  FULLSCREEN_NATIVE_ROTATION_90
  case  WINDOWED_ROTATION_90:
  case  FULLSCREEN_ROTATION_90:
  case  WINDOWED_CENTER_ROTATION_90:
    if (!pRotationDisplay->_90()) {
      MessageBox(NULL, "Valor de rotación 90 incorrecto", "Informacion", 0);
      ExitProcess(-3);
    }
    break;

  case  FULLSCREEN_NATIVE_ROTATION_180:
  case  FULLSCREEN_ROTATION_180:
  case  WINDOWED_CENTER_ROTATION_180:
  case  WINDOWED_ROTATION_180:
    if (!pRotationDisplay->_180()) {
      MessageBox(NULL, "Valor de rotación 180 incorrecto", "Informacion", 0);
      ExitProcess(-3);
    }
    break;
    
  case  FULLSCREEN_NATIVE_ROTATION_270:
  case  WINDOWED_ROTATION_270:
  case  FULLSCREEN_ROTATION_270:
  case  WINDOWED_CENTER_ROTATION_270:
    if (!pRotationDisplay->_270()) {
      MessageBox(NULL, "Valor de rotación 270 incorrecto", "Informacion", 0);
      ExitProcess(-3);
    }
    break;
    
  case  FULLSCREEN_NATIVE :
  case FULLSCREEN_NATIVE :
  case FULLSCREEN :
  case WINDOWED :
  case WINDOWED_CENTER :
  break;
   
  default: { 
    MessageBox(NULL, "Display desconocido","ERROR",MB_OK);
  }
}
```

Refactor: [unique_ptr & make_ptr](https://github.com/vicboma1/loaderDumpsArcade/issues/45)
