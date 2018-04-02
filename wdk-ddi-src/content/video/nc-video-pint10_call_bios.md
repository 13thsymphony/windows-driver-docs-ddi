---
UID: NC:video.PINT10_CALL_BIOS
title: PINT10_CALL_BIOS
author: windows-driver-content
description: The Int10CallBios function allows a miniport driver to call the kernel to perform an INT 10h operation, causing the BIOS ROM code on the device to execute natively.
old-location: display\int10callbios.htm
old-project: display
ms.assetid: 994a73bc-81a1-4d73-959c-cc89b242c073
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: Int10CallBios, Int10CallBios callback function [Display Devices], PINT10_CALL_BIOS, VideoPort_Functions_7a9921fa-ea1e-49fa-8881-ea0792d91123.xml, display.int10callbios, video/Int10CallBios
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	Int10CallBios
product:
- Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
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

Pointer to a video port driver-defined context for the interface. This should be the same as the value in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a> structure after <a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a> returns.

`BiosArguments`

Pointer to a video miniport driver-initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff567731">INT10_BIOS_ARGUMENTS</a> structure containing the values of the x86 registers. Any registers that are not needed in the INT10 BIOS call should be set to 0. When the function returns, some members of the INT10_BIOS_ARGUMENTS structures can have different values than before the call.


## Return Value

The <b>Int10CallBios</b> function returns NO_ERROR upon success. Otherwise it returns an appropriate error code.

## Remarks

The video port implements this function, which can be accessed through a pointer in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a>