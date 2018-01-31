---
UID : NS:video._VIDEO_PORT_I2C_INTERFACE
title : "_VIDEO_PORT_I2C_INTERFACE"
author : windows-driver-content
description : The VIDEO_PORT_I2C_INTERFACE structure describes the I2C service routines provided by the video port driver.
old-location : display\video_port_i2c_interface.htm
old-project : display
ms.assetid : fcc2679c-9a73-4bd0-ad2d-e7b48df9c7f7
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : VIDEO_PORT_I2C_INTERFACE structure [Display Devices], _VIDEO_PORT_I2C_INTERFACE, PVIDEO_PORT_I2C_INTERFACE, video/VIDEO_PORT_I2C_INTERFACE, VIDEO_PORT_I2C_INTERFACE, Video_Structs_2b152aec-acc0-4602-80de-cfdf9c0632a4.xml, PVIDEO_PORT_I2C_INTERFACE structure pointer [Display Devices], video/PVIDEO_PORT_I2C_INTERFACE, *PVIDEO_PORT_I2C_INTERFACE, display.video_port_i2c_interface
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : video.h
req.include-header : Video.h
req.target-type : Windows
req.target-min-winverclnt : 
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
req.irql : See Remarks section.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : VIDEO_PORT_I2C_INTERFACE, *PVIDEO_PORT_I2C_INTERFACE
req.product : Windows 10 or later.
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


`Context`

Pointer to a miniport driver-defined context for the interface.

`I2CRead`

Pointer to the video port driver's <a href="..\video\nc-video-pi2c_read.md">I2CRead</a> routine.

`I2CStart`

Pointer to the video port driver's <a href="..\video\nc-video-pi2c_start.md">I2CStart</a> routine.

`I2CStop`

Pointer to the video port driver's <a href="..\video\nc-video-pi2c_stop.md">I2CStop</a> routine.

`I2CWrite`

Pointer to the video port driver's <a href="..\video\nc-video-pi2c_write.md">I2CWrite</a> routine.

`InterfaceDereference`

Pointer to the video port driver-implemented dereference routine for this interface.

`InterfaceReference`

Pointer to the video port driver-implemented reference routine for this interface.

`Size`

Specifies the size in bytes of this structure.

`Version`

Specifies the version of the interface to be returned by the miniport driver. The current interface version is defined in <i>video.h</i>, and has the form VIDEO_PORT_I2C_INTERFACE_<i>N</i>.

## Remarks
PnP video miniport drivers that can use I²C should fill in the <b>Size</b> and <b>Version</b> members of this structure, and then call <a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a>, which initializes the remaining members of this structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | video.h (include Video.h) |

## See Also

<a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a>

<a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_PORT_I2C_INTERFACE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>