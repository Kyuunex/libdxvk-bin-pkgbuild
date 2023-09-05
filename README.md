# libdxvk-bin-pkgbuild
Just a PKGBUILD for Arch to install binary release of DXVK-native

## Example use

### Valve games:
Typical:
```
DXVK_HUD=version,compiler LD_PRELOAD="/usr/lib/libdxvk_d3d9.so:/usr/lib32/libdxvk_d3d9.so" %command% -novid -nojoy -fullscreen -vulkan +fps_max 200
```

Native Wayland:
```
DXVK_HUD=version,compiler LD_PRELOAD="/usr/lib/libSDL2-2.0.so:/usr/lib32/libSDL2-2.0.so:/usr/lib/libdxvk_d3d9.so:/usr/lib32/libdxvk_d3d9.so" %command% -novid -nojoy -fullscreen -vulkan +fps_max 200
```

don't blame me if u get VAC for this btw
