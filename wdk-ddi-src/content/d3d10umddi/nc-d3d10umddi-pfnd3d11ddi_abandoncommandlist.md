---
UID: NC:d3d10umddi.PFND3D11DDI_ABANDONCOMMANDLIST
title: PFND3D11DDI_ABANDONCOMMANDLIST
author: windows-driver-content
description: The AbandonCommandList function abandons the command list.
old-location: display\abandoncommandlist.htm
old-project: display
ms.assetid: fc8347da-25ac-47ea-b482-61b7873ca5bc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AbandonCommandList, AbandonCommandList callback function [Display Devices], PFND3D11DDI_ABANDONCOMMANDLIST, UserModeDisplayDriverDx11_Functions_1f9b5b27-499e-41a0-adf3-7b1c2f0021c7.xml, d3d10umddi/AbandonCommandList, display.abandoncommandlist
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: AbandonCommandList is supported beginning with the Windows 7 operating system.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	AbandonCommandList
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11DDI_ABANDONCOMMANDLIST callback function
The <b>AbandonCommandList</b> function abandons the command list.

## Syntax

```
PFND3D11DDI_ABANDONCOMMANDLIST Pfnd3d11ddiAbandoncommandlist;

void Pfnd3d11ddiAbandoncommandlist(
   D3D10DDI_HDEVICE
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`




## Return Value

None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set a critical error code. For more information about setting error codes, see the Remarks section.

## Remarks

After a deferred context is abandoned, the Direct3D runtime calls <b>AbandonCommandList</b> to abandon the command list that is associated with the deferred context. <b>AbandonCommandList</b> can apply state into whatever the driver prefers. 

The driver is only required to implement <b>AbandonCommandList</b> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability that can be returned in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542163">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="https://msdn.microsoft.com/83cd5f34-5f12-4ead-ad33-366fc3c6e804">GetCaps(D3D10_2)</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | AbandonCommandList is supported beginning with the Windows 7 operating system.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542163">D3D11DDI_THREADING_CAPS</a>



<a href="https://msdn.microsoft.com/83cd5f34-5f12-4ead-ad33-366fc3c6e804">GetCaps(D3D10_2)</a>