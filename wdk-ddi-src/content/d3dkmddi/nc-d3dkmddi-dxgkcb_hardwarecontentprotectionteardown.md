---
UID: NC:d3dkmddi.DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN
title: DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN
author: windows-driver-content
description: DxgkCbHardwareContentProtectionTeardown is used to indicate when a hardware content protection event occurs.
old-location: display\dxgkcbhardwarecontentprotectionteardown.htm
old-project: display
ms.assetid: 7B12B9AD-2288-4CE0-A4D8-F1C96150CE45
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkcbhardwarecontentprotectionteardown, DxgkCbHardwareContentProtectionTeardown callback function [Display Devices], DxgkCbHardwareContentProtectionTeardown, DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN, DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN, d3dkmddi/DxgkCbHardwareContentProtectionTeardown
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DxgkCbHardwareContentProtectionTeardown
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN callback function
<b>DxgkCbHardwareContentProtectionTeardown</b> is used to indicate when a hardware content protection event occurs.

## Syntax

```
DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN DxgkcbHardwarecontentprotectionteardown;

void DxgkcbHardwarecontentprotectionteardown(
  IN_CONST_HANDLE hAdapter,
  UINT Flags
)
{...}
```

## Parameters

`hAdapter`

A handle to the graphics adapter where the tear-down event is occurring.

`Flags`

Additional flags defined by <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_hardware_content_protection_teardown_flags.md">DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS</a> enumeration.


## Return Value

This callback function does not return a value.

## Remarks

The kernel mode driver should always call this callback before and after a hardware content protection tear-down event occurs.



The driver can call this callback at either passive level or at dispatch level.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_hardware_content_protection_teardown_flags.md">DXGK_HARDWARE_CONTENT_PROTECTION_TEARDOWN_FLAGS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_HARDWARECONTENTPROTECTIONTEARDOWN callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>