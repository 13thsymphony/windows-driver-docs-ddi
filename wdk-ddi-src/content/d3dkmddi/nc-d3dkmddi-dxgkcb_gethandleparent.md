---
UID: NC:d3dkmddi.DXGKCB_GETHANDLEPARENT
title: DXGKCB_GETHANDLEPARENT
author: windows-driver-content
description: The DxgkCbGetHandleParent function retrieves the parent resource from the specified allocation.
old-location: display\dxgkcbgethandleparent.htm
old-project: display
ms.assetid: db8e7a91-d62a-4d2f-ac21-266e365a352c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkcbgethandleparent, DxgkCbGetHandleParent callback function [Display Devices], DxgkCbGetHandleParent, DXGKCB_GETHANDLEPARENT, DXGKCB_GETHANDLEPARENT, d3dkmddi/DxgkCbGetHandleParent, DpFunctions_7094d9b1-3262-45b9-88de-e834878b6b2d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: "< DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DxgkCbGetHandleParent
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKCB_GETHANDLEPARENT callback function
The <b>DxgkCbGetHandleParent</b> function retrieves the parent resource from the specified allocation.

## Syntax

```
DXGKCB_GETHANDLEPARENT DxgkcbGethandleparent;

D3DKMT_HANDLE DxgkcbGethandleparent(
  IN_D3DKMT_HANDLE hAllocation
)
{...}
```

## Parameters

`hAllocation`

[in] A handle to an allocation. This handle must be the kernel-mode handle that the Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) assigned for the allocation.


## Return Value

<b>DxgkCbGetHandleParent</b> returns a graphics subsystem-specific handle to the parent resource for the allocation that is associated with the handle that the <i>hAllocation</i> parameter specifies.

If <i>DxgkCbGetHandleParent</i> returns a <b>NULL</b> handle, the DirectX graphics kernel subsystem was unable to resolve the handle to the parent resource because, for example, of the following possible reasons:



<ul>
<li>An invalid handle was received from the user-mode display driver because of a malicious attack or some other bug.</li>
<li>Allocations had lifetime issues. </li>
</ul>
If a <b>NULL</b> handle is returned, the display miniport driver should fail its currently running DDI function with STATUS_INVALID_HANDLE.

## Remarks

For <b>DxgkCbGetHandleParent</b> to return a resource handle, the handle in <i>hAllocation</i> must be an allocation handle that is associated with a resource; otherwise, <b>DxgkCbGetHandleParent</b> returns <b>NULL</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
| **IRQL** | "< DISPATCH_LEVEL" |