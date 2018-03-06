---
UID: NC:d3dkmddi.DXGKDDI_RENDERGDI
title: DXGKDDI_RENDERGDI
author: windows-driver-content
description: DxgkDdiRenderGdi is used when submitting Windows Graphics Device Interface (GDI) commands for contexts that support virtual addressing.
old-location: display\dxgkddirendergdi.htm
old-project: display
ms.assetid: 90C34125-FC32-46E3-81F7-6B2AACED9BAC
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_RENDERGDI, DxgkDdiRenderGdi, DxgkDdiRenderGdi callback function [Display Devices], d3dkmddi/DxgkDdiRenderGdi, display.dxgkddirendergdi
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiRenderGdi
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_RENDERGDI callback function
<b>DxgkDdiRenderGdi</b> is used when submitting Windows Graphics Device Interface (GDI) commands for contexts that support virtual addressing.

## Syntax

```
DXGKDDI_RENDERGDI DxgkddiRendergdi;

NTSTATUS DxgkddiRendergdi(
  IN_CONST_HANDLE hContext,
  INOUT_PDXGKARG_RENDERGDI pRenderGdi
)
{...}
```

## Parameters

`hContext`

A handle to a context block that is associated with a display adapter.

`pRenderGdi`

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_rendergdi.md">DXGKARG_RENDERGDI</a> structure that describes operation.


## Return Value

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_SUCCESS</dt>
</dl>
</td>
<td width="60%">
The submitted command is well-formed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>(other)</dt>
</dl>
</td>
<td width="60%">
All other return values will lead to the OS <i>bugcheck</i>.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h |

## See Also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_rendergdi.md">DXGKARG_RENDERGDI</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_RENDERGDI callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>