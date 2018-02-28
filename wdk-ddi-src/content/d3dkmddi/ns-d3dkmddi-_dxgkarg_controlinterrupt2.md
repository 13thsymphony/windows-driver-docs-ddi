---
UID: NS:d3dkmddi._DXGKARG_CONTROLINTERRUPT2
title: "_DXGKARG_CONTROLINTERRUPT2"
author: windows-driver-content
description: The DXGKARG_CONTROLINTERRUPT2 structure is used in DxgkDdi_ControlInterrupt2 calls to describe the state of interrupts.
old-location: display\dxgkarg_controlinterrupt2.htm
old-project: display
ms.assetid: 881F93B2-999F-4E3A-A71D-731946E8AA97
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: DXGKARG_CONTROLINTERRUPT2, DXGKARG_CONTROLINTERRUPT2 structure [Display Devices], DXGKARG_CONTROLINTTERUPT2, DXGKARG_CONTROLINTTERUPT2 structure [Display Devices], _DXGKARG_CONTROLINTERRUPT2, d3dkmddi/DXGKARG_CONTROLINTERRUPT2, display.dxgkarg_controlinterrupt2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10 and later versions of the Windows operating systems.
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
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_CONTROLINTTERUPT2
product: Windows
targetos: Windows
req.typenames: DXGKARG_CONTROLINTERRUPT2
---

# _DXGKARG_CONTROLINTERRUPT2 structure
The DXGKARG_CONTROLINTERRUPT2 structure is used in <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_controlinterrupt2.md">DxgkDdi_ControlInterrupt2</a> calls to describe the state of interrupts.

## Syntax
````
typedef struct _DXGKARG_CONTROLINTERRUPT2 {
  DXGK_INTERRUPT_STATE  InterruptState;
  DXGK_CRTC_VSYNC_STATE CrtcVsyncState;
} DXGKARG_CONTROLINTTERUPT2;
````

## Members


`InterruptType`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 10 and later versions of the Windows operating systems. Available in Windows 10 and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_controlinterrupt2.md">DxgkDdi_ControlInterrupt2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_CONTROLINTERRUPT2 structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>