# DirectX Texture Converter 2017
<p>This is more or less just a backup of Microsoft's Texture Converter from 2017 that is needed by many games of the timeframe (DX9-DX12). I am not the author of these binaries, I am simply preserving them to aid modders in the modding of Space Engineers or any other games.
<p> ~
# Sources:
<p>The original github where they keep the most updated version is here:
<p>https://github.com/microsoft/DirectXTex/releases
<p><p>Related documentation on the most up-to-date version can be found here:
<p>https://github.com/Microsoft/DirectXTex/wiki/Texconv
<p> ~
<p><p>The primary backups (dated 2017-11-26) of texconv.exe and texassemble.exe came from Keen's Space Engineers directory in Steam:
<p><img src="https://github.com/DranKof/DirectX-Texture-Converter-2017/blob/master/Finding%20TexConv.png">
<p><p>The primary backup (dated 2017-09-22) of texdiag.exe came from here:
<p>https://github.com/microsoft/DirectXTex/releases/tag/sept2017
<p><p>The secondary backups (the ones I've tested the most, dated 2017-07-26) came from:
<p>https://github.com/microsoft/DirectXTex/releases/tag/jul2017
<p> ~
<p><p>My Guide on using this to make and edit DDS hud icons for Space Engineers is here:
<p>https://steamcommunity.com/sharedfiles/filedetails/?id=1116386590

------------------------------------
# texconv.exe Syntax

```
Microsoft (R) DirectX Texture Converter (DirectXTex version)
Copyright (C) Microsoft Corp. All rights reserved.

Usage: texconv <options> <files>

   -r                  wildcard filename search is recursive
   -w <n>              width
   -h <n>              height
   -m <n>              miplevels
   -f <format>         format
   -if <filter>        image filtering
   -srgb{i|o}          sRGB {input, output}
   -px <string>        name prefix
   -sx <string>        name suffix
   -o <directory>      output directory
   -y                  overwrite existing output file (if any)
   -ft <filetype>      output file type
   -hflip              horizonal flip of source image
   -vflip              vertical flip of source image
   -sepalpha           resize/generate mips alpha channel separately
                       from color channels
   -wrap, -mirror      texture addressing mode (wrap, mirror, or clamp)
   -pmalpha            convert final texture to use premultiplied alpha
   -alpha              convert premultiplied alpha to straight alpha
   -pow2               resize to fit a power-of-2, respecting aspect ratio
   -nmap <options>     converts height-map to normal-map
                       options must be one or more of
                          r, g, b, a, l, m, u, v, i, o
   -nmapamp <weight>   normal map amplitude (defaults to 1.0)
   -fl <feature-level> Set maximum feature level target (defaults to 11.0)

                       (DDS input only)
   -t{u|f}             TYPELESS format is treated as UNORM or FLOAT
   -dword              Use DWORD instead of BYTE alignment
   -badtails           Fix for older DXTn with bad mipchain tails
   -xlum               expand legacy L8, L16, and A8P8 formats

                       (DDS output only)
   -dx10               Force use of 'DX10' extended header

   -nologo             suppress copyright message
   -timing             Display elapsed processing time

   -singleproc         Do not use multi-threaded compression
   -gpu <adapter>      Select GPU for DirectCompute-based codecs (0 is default)
   -nogpu              Do not use DirectCompute-based codecs
   -bcuniform          Use uniform rather than perceptual weighting for BC1-3
   -bcdither           Use dithering for BC1-3
   -bcmax              Use exhaustive compression (BC7 only)
   -bcquick            Use quick compression (BC7 only)
   -wicq <quality>     When writing images with WIC use quality (0.0 to 1.0)
   -wiclossless        When writing images with WIC use lossless mode
   -aw <weight>        BC7 GPU compressor weighting for alpha error metric
                       (defaults to 1.0)
   -c <hex-RGB>        colorkey (a.k.a. chromakey) transparency
   -tonemap            Apply a tonemap operator based on maximum luminance
   -x2bias             Enable *2 - 1 conversion cases for unorm/pos-only-float

   <format>: R32G32B32A32_FLOAT R32G32B32A32_UINT R32G32B32A32_SINT
      R32G32B32_FLOAT R32G32B32_UINT R32G32B32_SINT R16G16B16A16_FLOAT
      R16G16B16A16_UNORM R16G16B16A16_UINT R16G16B16A16_SNORM
      R16G16B16A16_SINT R32G32_FLOAT R32G32_UINT R32G32_SINT
      R10G10B10A2_UNORM R10G10B10A2_UINT R11G11B10_FLOAT R8G8B8A8_UNORM
      R8G8B8A8_UNORM_SRGB R8G8B8A8_UINT R8G8B8A8_SNORM R8G8B8A8_SINT
      R16G16_FLOAT R16G16_UNORM R16G16_UINT R16G16_SNORM R16G16_SINT
      R32_FLOAT R32_UINT R32_SINT R8G8_UNORM R8G8_UINT R8G8_SNORM
      R8G8_SINT R16_FLOAT R16_UNORM R16_UINT R16_SNORM R16_SINT
      R8_UNORM R8_UINT R8_SNORM R8_SINT A8_UNORM R9G9B9E5_SHAREDEXP
      R8G8_B8G8_UNORM G8R8_G8B8_UNORM BC1_UNORM BC1_UNORM_SRGB BC2_UNORM
      BC2_UNORM_SRGB BC3_UNORM BC3_UNORM_SRGB BC4_UNORM BC4_SNORM
      BC5_UNORM BC5_SNORM B5G6R5_UNORM B5G5R5A1_UNORM B8G8R8A8_UNORM
      B8G8R8X8_UNORM R10G10B10_XR_BIAS_A2_UNORM B8G8R8A8_UNORM_SRGB
      B8G8R8X8_UNORM_SRGB BC6H_UF16 BC6H_SF16 BC7_UNORM BC7_UNORM_SRGB
      AYUV Y410 Y416 YUY2 Y210 Y216 B4G4R4A4_UNORM

   <filter>: POINT LINEAR CUBIC FANT BOX TRIANGLE POINT_DITHER
      LINEAR_DITHER CUBIC_DITHER FANT_DITHER BOX_DITHER TRIANGLE_DITHER
      POINT_DITHER_DIFFUSION LINEAR_DITHER_DIFFUSION CUBIC_DITHER_DIFFUSION
      FANT_DITHER_DIFFUSION BOX_DITHER_DIFFUSION TRIANGLE_DITHER_DIFFUSION

   <filetype>: BMP JPG JPEG PNG DDS TGA HDR TIF TIFF WDP HDP JXR

   <feature-level>: 9.1 9.2 9.3 10.0 10.1 11.0 11.1 12.0 12.1

   <adapter>:
      0: VID:10DE, PID:1B81 - NVIDIA GeForce GTX 1070
      1: VID:8086, PID:193B - Intel(R) Iris(R) Pro Graphics 580
      2: VID:1414, PID:008C - Microsoft Basic Render Driver
```

------------------------------------
# Useful Batch Script (convertTextures.bat)
   
```bat
texconv -f BC7_UNORM_SRGB -if LINEAR -sRGB -y -o TexturesOut -pmalpha Textures\*.dds
ren TexturesOut\*.DDS *.dds
pause
```
   
------------------------------------
# texdiag.exe Syntax
   
```
Microsoft (R) DirectX Texture Diagnostic Tool
Copyright (C) Microsoft Corp. All rights reserved.

Usage: texdiag <command> <options> <files>

   info                Output image metadata
   analyze             Analyze and summarize image information
   compare             Compare two images with MSE error metric
   diff                Generate difference image from two images
   dumpbc              Dump out compressed blocks (DDS BC only)

   -r                  wildcard filename search is recursive
   -if <filter>        image filtering

                       (DDS input only)
   -t{u|f}             TYPELESS format is treated as UNORM or FLOAT
   -dword              Use DWORD instead of BYTE alignment
   -badtails           Fix for older DXTn with bad mipchain tails
   -xlum               expand legacy L8, L16, and A8P8 formats

                       (diff only)
   -f <format>         format
   -o <filename>       output filename
   -y                  overwrite existing output file (if any)

                       (dumpbc only)
   -targetx <num>      dump pixels at location x (defaults to all)
   -targety <num>      dump pixels at location y (defaults to all)

   -nologo             suppress copyright message
   -flist <filename>   use text file with a list of input files (one per line)

   <format>: R32G32B32A32_FLOAT R32G32B32A32_UINT R32G32B32A32_SINT
      R32G32B32_FLOAT R32G32B32_UINT R32G32B32_SINT R16G16B16A16_FLOAT
      R16G16B16A16_UNORM R16G16B16A16_UINT R16G16B16A16_SNORM
      R16G16B16A16_SINT R32G32_FLOAT R32G32_UINT R32G32_SINT
      R10G10B10A2_UNORM R10G10B10A2_UINT R11G11B10_FLOAT R8G8B8A8_UNORM
      R8G8B8A8_UNORM_SRGB R8G8B8A8_UINT R8G8B8A8_SNORM R8G8B8A8_SINT
      R16G16_FLOAT R16G16_UNORM R16G16_UINT R16G16_SNORM R16G16_SINT
      R32_FLOAT R32_UINT R32_SINT R8G8_UNORM R8G8_UINT R8G8_SNORM
      R8G8_SINT R16_FLOAT R16_UNORM R16_UINT R16_SNORM R16_SINT
      R8_UNORM R8_UINT R8_SNORM R8_SINT A8_UNORM R9G9B9E5_SHAREDEXP
      R8G8_B8G8_UNORM G8R8_G8B8_UNORM B5G6R5_UNORM B5G5R5A1_UNORM
      B8G8R8A8_UNORM B8G8R8X8_UNORM R10G10B10_XR_BIAS_A2_UNORM
      B8G8R8A8_UNORM_SRGB B8G8R8X8_UNORM_SRGB AYUV Y410 Y416 YUY2 Y210
      Y216 B4G4R4A4_UNORM

   <filter>: POINT LINEAR CUBIC FANT BOX TRIANGLE POINT_DITHER
      LINEAR_DITHER CUBIC_DITHER FANT_DITHER BOX_DITHER TRIANGLE_DITHER
      POINT_DITHER_DIFFUSION LINEAR_DITHER_DIFFUSION CUBIC_DITHER_DIFFUSION
      FANT_DITHER_DIFFUSION BOX_DITHER_DIFFUSION TRIANGLE_DITHER_DIFFUSION
```
   
------------------------------------
# Sample Batch Script (analyze.bat)

```bat
texdiag info *.dds
texdiag info Textures\*.dds
texdiag info TexturesOut\*.dds
pause
```

------------------------------------
# texassemble.exe

```
Microsoft (R) DirectX Texture Assembler (DirectXTex version)
Copyright (C) Microsoft Corp. All rights reserved.

Usage: texassemble <command> <options> <files>

   cube                create cubemap
   volume              create volume map
   array               create texture array
   cubearray           create cubemap array
   h-cross or v-cross  create a cross image from a cubemap
   h-strip or v-strip  create a strip image from a cubemap

   -r                  wildcard filename search is recursive
   -w <n>              width
   -h <n>              height
   -f <format>         format
   -if <filter>        image filtering
   -srgb{i|o}          sRGB {input, output}
   -o <filename>       output filename
   -y                  overwrite existing output file (if any)
   -sepalpha           resize alpha channel separately from color channels
   -wrap, -mirror      texture addressing mode (wrap, mirror, or clamp)
   -alpha              convert premultiplied alpha to straight alpha
   -dx10               Force use of 'DX10' extended header
   -nologo             suppress copyright message

   <format>: R32G32B32A32_FLOAT R32G32B32A32_UINT R32G32B32A32_SINT
      R32G32B32_FLOAT R32G32B32_UINT R32G32B32_SINT R16G16B16A16_FLOAT
      R16G16B16A16_UNORM R16G16B16A16_UINT R16G16B16A16_SNORM
      R16G16B16A16_SINT R32G32_FLOAT R32G32_UINT R32G32_SINT
      R10G10B10A2_UNORM R10G10B10A2_UINT R11G11B10_FLOAT R8G8B8A8_UNORM
      R8G8B8A8_UNORM_SRGB R8G8B8A8_UINT R8G8B8A8_SNORM R8G8B8A8_SINT
      R16G16_FLOAT R16G16_UNORM R16G16_UINT R16G16_SNORM R16G16_SINT
      R32_FLOAT R32_UINT R32_SINT R8G8_UNORM R8G8_UINT R8G8_SNORM
      R8G8_SINT R16_FLOAT R16_UNORM R16_UINT R16_SNORM R16_SINT
      R8_UNORM R8_UINT R8_SNORM R8_SINT A8_UNORM R9G9B9E5_SHAREDEXP
      R8G8_B8G8_UNORM G8R8_G8B8_UNORM B5G6R5_UNORM B5G5R5A1_UNORM
      B8G8R8A8_UNORM B8G8R8X8_UNORM R10G10B10_XR_BIAS_A2_UNORM
      B8G8R8A8_UNORM_SRGB B8G8R8X8_UNORM_SRGB AYUV Y410 Y416 YUY2 Y210
      Y216 B4G4R4A4_UNORM

   <filter>: POINT LINEAR CUBIC FANT BOX TRIANGLE POINT_DITHER
      LINEAR_DITHER CUBIC_DITHER FANT_DITHER BOX_DITHER TRIANGLE_DITHER
      POINT_DITHER_DIFFUSION LINEAR_DITHER_DIFFUSION CUBIC_DITHER_DIFFUSION
      FANT_DITHER_DIFFUSION BOX_DITHER_DIFFUSION TRIANGLE_DITHER_DIFFUSION
```

------------------------------------
# Sample Batch Script
<p>I've never used this. Good luck!
