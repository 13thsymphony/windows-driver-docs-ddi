---
UID : NC:video.PINT10_CALL_BIOS
title : PINT10_CALL_BIOS
author : windows-driver-content
description : The Int10CallBios function allows a miniport driver to call the kernel to perform an INT 10h operation, causing the BIOS ROM code on the device to execute natively.
old-location : display\int10callbios.htm
old-project : display
ms.assetid : 994a73bc-81a1-4d73-959c-cc89b242c073
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.int10callbios, Int10CallBios callback function [Display Devices], Int10CallBios, PINT10_CALL_BIOS, PINT10_CALL_BIOS, video/Int10CallBios, VideoPort_Functions_7a9921fa-ea1e-49fa-8881-ea0792d91123.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : video.h
req.include-header : Video.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows 2000 and later versions of the Windows operating systems.
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : VHF_CONFIG, *PVHF_CONFIG
req.product : Windows 10 or later.
---


# PINT10_CALL_BIOS callback function
The <i>Int10CallBios</i> function allows a miniport driver to call the kernel to perform an INT 10h operation, causing the BIOS ROM code on the device to execute natively.

## Syntax

```
PINT10_CALL_BIOS Pint10CallBios;

VP_STATUS Pint10CallBios(
  PVOID Context,
  PINT10_BIOS_ARGUMENTS BiosArguments
)
{...}
```

## Parameters

`Context`

Pointer to a video port driver-defined context for the interface. This should be the same as the value in the <b>Context</b> member of the <a href="..\video\ns-video-_video_port_int10_interface.md">VIDEO_PORT_INT10_INTERFACE</a> structure after <a href="..\video\nf-video-videoportqueryservices.md">VideoPortQueryServices</a> returns.

`BiosArguments`

Pointer to a video miniport driver-initialized <a href="..\video\ns-video-_int10_bios_arguments.md">INT10_BIOS_ARGUMENTS</a> structure containing the values of the x86 registers. Any registers that are not needed in the INT10 BIOS call should be set to 0. When the function returns, some members of the INT10_BIOS_ARGUMENTS structures can have different values than before the call.


## Return Value

The <b>Int10CallBios</b> function returns NO_ERROR upon success. Otherwise it returns an appropriate error code.

## Remarks

The video port implements this function, which can be accessed through a pointer in the <a href="..\video\ns-video-_video_port_int10_interface.md">VIDEO_PORT_INT10_INTERFACE</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | video.h (include Video.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\video\ns-video-_video_port_int10_interface.md">VIDEO_PORT_INT10_INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PINT10_CALL_BIOS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>