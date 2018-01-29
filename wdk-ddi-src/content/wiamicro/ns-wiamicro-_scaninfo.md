---
UID : NS:wiamicro._SCANINFO
title : _SCANINFO
author : windows-driver-content
description : The SCANINFO structure is used to store and communicate information about a scan acquisition.
old-location : image\scaninfo.htm
old-project : image
ms.assetid : 58a0cc96-7180-4823-a4af-bf2d5fa49474
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : image.scaninfo, *PSCANINFO, SCANINFO structure [Imaging Devices], MicroDrv_42f31c58-206a-468e-98ff-794c69b82457.xml, PSCANINFO structure pointer [Imaging Devices], PSCANINFO, _SCANINFO, wiamicro/PSCANINFO, SCANINFO, wiamicro/SCANINFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wiamicro.h
req.include-header : Wiamicro.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SCANINFO, *PSCANINFO
req.product : Windows 10 or later.
---

# _SCANINFO structure
The SCANINFO structure is used to store and communicate information about a scan acquisition. The WIA Flatbed Driver reads values from the SCANINFO structure, but never writes values. It is the microdriver's responsibility to set values for the SCANINFO members.

## Syntax
````
typedef struct _SCANINFO {
  LONG       ADF;
  LONG       TPA;
  LONG       Endorser;
  LONG       OpticalXResolution;
  LONG       OpticalYResolution;
  LONG       BedWidth;
  LONG       BedHeight;
  RANGEVALUE IntensityRange;
  RANGEVALUE ContrastRange;
  LONG       SupportedCompressionType;
  LONG       SupportedDataTypes;
  LONG       WidthPixels;
  LONG       WidthBytes;
  LONG       Lines;
  LONG       DataType;
  LONG       PixelBits;
  LONG       Intensity;
  LONG       Contrast;
  LONG       Xresolution;
  LONG       Yresolution;
  SCANWINDOW Window;
  LONG       DitherPattern;
  LONG       Negative;
  LONG       Mirror;
  LONG       AutoBack;
  LONG       ColorDitherPattern;
  LONG       ToneMap;
  LONG       Compression;
  LONG       RawDataFormat;
  LONG       RawPixelOrder;
  LONG       bNeedDataAlignment;
  LONG       DelayBetweenRead;
  LONG       MaxBufferSize;
  HANDLE     DeviceIOHandles[MAX_IO_HANDLES];
  LONG       lReserved[MAX_RESERVED];
  VOID       *pMicroDriverContext;
} SCANINFO, *PSCANINFO;
````

## Members


`ADF`

Indicates whether the scanner supports an automatic document feeder (ADF). This member can be one of the following values:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
0

</td>
<td>
The scanner does not support an ADF.

</td>
</tr>
<tr>
<td>
1

</td>
<td>
The scanner supports an ADF.

</td>
</tr>
<tr>
<td>
2

</td>
<td>
The scanner supports an ADF with duplex capability.

</td>
</tr>
</table>

`AutoBack`

Specifies whether AutoBack is on or off. The value can be:

0 - off

1 - on

`BedHeight`

Specifies the bed height of the scanner in thousandths of an inch.

`BedWidth`

Specifies the bed width of the scanner in thousandths of an inch.

`bNeedDataAlignment`

Specifies whether data alignment is needed for the scanner. The value can be:

0 - false

1 - true

`ColorDitherPattern`

Reserved. Set to zero.

`Compression`

Specifies whether compression is on or off for the scanner. The value can be:

0 - off

1 - on

`Contrast`

Specifies the current contrast setting of the scanner.

`ContrastRange`

Specifies the contrast range values of the scanner.

`DataType`

Specifies the current data type set of the current image. This member can be set to one of the following.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WIA_DATA_COLOR

</td>
<td>
The driver supports 24 bit-per-pixel color.

</td>
</tr>
<tr>
<td>
WIA_DATA_COLOR_DITHER

</td>
<td>
This value is not supported in the WIA Flatbed driver.

</td>
</tr>
<tr>
<td>
WIA_DATA_COLOR_THRESHOLD

</td>
<td>
This value is not supported in the WIA Flatbed driver.

</td>
</tr>
<tr>
<td>
WIA_DATA_DITHER

</td>
<td>
This value is not supported in the WIA Flatbed driver.

</td>
</tr>
<tr>
<td>
WIA_DATA_GRAYSCALE

</td>
<td>
The driver supports 8 bit-per-pixel grayscale.

</td>
</tr>
<tr>
<td>
WIA_DATA_THRESHOLD

</td>
<td>
The driver supports 1 bit-per-pixel black and white.

</td>
</tr>
</table>

`DelayBetweenRead`

Specifies the time delay in milliseconds between <a href="..\wiamicro\nf-wiamicro-scan.md">Scan</a> function calls that the scanner can support.

`DeviceIOHandles`

Specifies an array of device I/O handles needed for device communication.

`DitherPattern`

Specifies the dither pattern of the scanner.

`Endorser`

Indicates whether the scanner has endorser capabilities. The value can be:

0 - not supported

1 - supported

`Intensity`

Specifies the current intensity/brightness setting of the scanner.

`IntensityRange`

Specifies the intensity/brightness range values of the scanner.

`Lines`

Specifies the height of the current image in pixels.

`lReserved`

Specifies an array of reserved bits.

`MaxBufferSize`

Specifies the maximum buffer size in the scanner.

`Mirror`

Specifies whether mirror is on or off. The value can be:

0 - off

1 - on

`Negative`

Specifies whether negative is on or off. The value can be:

0 - off

1 - on

`OpticalXResolution`

Specifies the horizontal dpi setting of the scanner optics.

`OpticalYResolution`

Specifies the vertical dpi setting of the scanner optics.

`PixelBits`

Specifies the current bit depth setting of the current image.

`pMicroDriverContext`

Points to the microdriver's context. <i>This member is defined only for Microsoft Windows XP and later</i>. The microdriver allocates the buffer pointed to by this member. The buffer should be allocated in CMD_INITIALIZE, and freed in CMD_UNINITIALIZE. (See <a href="https://msdn.microsoft.com/library/windows/hardware/ff547067">Required Commands</a>.) The WIA Flatbed driver knows nothing of this pointer, and hence will not alter the memory pointed to by this member.

`RawDataFormat`

Specifies the raw data format for the scanner. The value can be:

0 - packed data

1 - planar data

`RawPixelOrder`

Specifies the pixel order for the scanner. The value can be:

0 - RGB

1 - BGR

`SupportedCompressionType`

Specifies a mask value of supported compression types. A value of zero indicates that no compression types are supported.

`SupportedDataTypes`

Specifies a mask value of supported data types. A value of zero indicates that no data types are supported. This member can be the bitwise OR of the following.
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
SUPPORT_BW

</td>
<td>
The image is 1 bit-per-pixel black and white.

</td>
</tr>
<tr>
<td>
SUPPORT_COLOR

</td>
<td>
The image is 24 bits-per-pixel color.

</td>
</tr>
<tr>
<td>
SUPPORT_GRAYSCALE

</td>
<td>
The image is 8 bits-per-pixel grayscale.

</td>
</tr>
</table>

`ToneMap`

Reserved. Set to zero.

`TPA`

Indicates whether the scanner supports TPA (TransParency Adapter). The value can be:

0 - not supported

1 - supported

`WidthBytes`

Specifies the width of the current image in bytes.

`WidthPixels`

Specifies the width of the current image in pixels.

`Window`

Specifies the current scanner window settings.

`Xresolution`

Specifies the horizontal dpi setting of the scanner optics.

`Yresolution`

Specifies the vertical dpi setting of the scanner optics.

## Remarks
This structure is used as a parameter in the microdriver's <a href="..\wiamicro\nf-wiamicro-setpixelwindow.md">SetPixelWindow</a>, and <a href="..\wiamicro\nf-wiamicro-scan.md">Scan</a> functions.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wiamicro.h (include Wiamicro.h) |

## See Also

<a href="..\wiamicro\nf-wiamicro-setpixelwindow.md">SetPixelWindow</a>

<a href="..\wiamicro\nf-wiamicro-scan.md">Scan</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20SCANINFO structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>