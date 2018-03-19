---
UID: NS:video._VIDEO_PORT_I2C_INTERFACE
title: "_VIDEO_PORT_I2C_INTERFACE"
author: windows-driver-content
description: The VIDEO_PORT_I2C_INTERFACE structure describes the I2C service routines provided by the video port driver.
old-location: display\video_port_i2c_interface.htm
old-project: display
ms.assetid: fcc2679c-9a73-4bd0-ad2d-e7b48df9c7f7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PVIDEO_PORT_I2C_INTERFACE, PVIDEO_PORT_I2C_INTERFACE, PVIDEO_PORT_I2C_INTERFACE structure pointer [Display Devices], VIDEO_PORT_I2C_INTERFACE, VIDEO_PORT_I2C_INTERFACE structure [Display Devices], Video_Structs_2b152aec-acc0-4602-80de-cfdf9c0632a4.xml, _VIDEO_PORT_I2C_INTERFACE, display.video_port_i2c_interface, video/PVIDEO_PORT_I2C_INTERFACE, video/VIDEO_PORT_I2C_INTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: video.h
req.include-header: Video.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	video.h
api_name:
-	VIDEO_PORT_I2C_INTERFACE
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_I2C_INTERFACE, *PVIDEO_PORT_I2C_INTERFACE
req.product: Windows 10 or later.
---

# _VIDEO_PORT_I2C_INTERFACE structure
The VIDEO_PORT_I2C_INTERFACE structure describes the <a href="https://msdn.microsoft.com/5a140cc0-ecc5-46ff-be3f-3c92f0f67dca">I2C</a> service routines provided by the video port driver.

## Syntax
````
typedef struct _VIDEO_PORT_I2C_INTERFACE {
  USHORT                 Size;
  USHORT                 Version;
  PVOID                  Context;
  PINTERFACE_REFERENCE   InterfaceReference;
  PINTERFACE_DEREFERENCE InterfaceDereference;
  PI2C_START             I2CStart;
  PI2C_STOP              I2CStop;
  PI2C_WRITE             I2CWrite;
  PI2C_READ              I2CRead;
} VIDEO_PORT_I2C_INTERFACE, *PVIDEO_PORT_I2C_INTERFACE;
````

## Members


`Size`

Specifies the size in bytes of this structure.

`Version`

Specifies the version of the interface to be returned by the miniport driver. The current interface version is defined in <i>video.h</i>, and has the form VIDEO_PORT_I2C_INTERFACE_<i>N</i>.

`Context`

Pointer to a miniport driver-defined context for the interface.

`InterfaceReference`

Pointer to the video port driver-implemented reference routine for this interface.

`InterfaceDereference`

Pointer to the video port driver-implemented dereference routine for this interface.

`I2CStart`

Pointer to the video port driver's <a href="..\video\nc-video-pi2c_start.md">I2CStart</a> routine.

`I2CStop`

Pointer to the video port driver's <a href="..\video\nc-video-pi2c_stop.md">I2CStop</a> routine.

`I2CWrite`

Pointer to the video port driver's <a href="..\video\nc-video-pi2c_write.md">I2CWrite</a> routine.

`I2CRead`

Pointer to the video port driver's <a href="..\video\nc-video-pi2c_read.md">I2CRead</a> routine.

## Remarks
PnP video miniport drivers that can use I²C should fill in the <b>Size</b> and <b>Version</b> members of this structure, and then call <a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a>, which initializes the remaining members of this structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | video.h (include Video.h) |

## See Also

<a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>



<a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a>