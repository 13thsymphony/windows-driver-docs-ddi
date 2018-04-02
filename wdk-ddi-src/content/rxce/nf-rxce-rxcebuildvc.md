---
UID: NF:rxce.RxCeBuildVC
title: RxCeBuildVC function
author: windows-driver-content
description: RxCeBuildVC adds a virtual circuit to a specified RDBSS connection..
old-location: ifsk\rxcebuildvc.htm
old-project: ifsk
ms.assetid: b060bd22-113f-4f78-8763-d1d19cf198b8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RxCeBuildVC, RxCeBuildVC function [Installable File System Drivers], ifsk.rxcebuildvc, rxce/RxCeBuildVC, rxref_4f4f58c7-5970-4a86-883e-359e92bddaa3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxce.h
req.include-header: Rxce.h
req.target-type: Desktop
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxce.h
api_name:
-	RxCeBuildVC
product: Windows
targetos: Windows
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---


# RxCeBuildVC function
<b>RxCeBuildVC</b> adds a virtual circuit to a specified RDBSS connection..

## Syntax

```
NTSTATUS RxCeBuildVC(
  IN OUT PRXCE_VC     pVc,
  IN PRXCE_CONNECTION Connection
);
```

## Parameters

`pVc`

On input, this parameter contains a pointer to a handle for an uninitialized virtual circuit. On output when this call is successful, the virtual circuit is associated with the specified connection and the state of the virtual circuit is initialized as active.

`Connection`

TBD


## Return Value

<b>RxCeBuildVC</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The allocation of nonpaged pool memory needed by this routine failed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the parameters passed to this routine was invalid. 

</td>
</tr>
</table>

## Remarks

When <b>RxCeBuildVC</b> is successful, the data members in the RXCE_VC structure pointed to by the <i>pVC</i> parameter will be properly initialized and the virtual circuit will be added to the specified RDBSS connection.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | rxce.h (include Rxce.h) |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554332">RxCeTearDownVC</a>