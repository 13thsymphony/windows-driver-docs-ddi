---
UID: NF:fltkernel.FltCheckAndGrowNameControl
title: FltCheckAndGrowNameControl function
author: windows-driver-content
description: The FltCheckAndGrowNameControl routine checks whether the buffer in a FLT_NAME_CONTROL structure is large enough to hold the specified number of bytes. If not, FltCheckAndGrowNameControl replaces it with a larger system-allocated buffer.
old-location: ifsk\fltcheckandgrownamecontrol.htm
old-project: ifsk
ms.assetid: 0a49e69e-6b6b-4f86-bd41-d1ad73e63a17
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_5ab0b3b3-adeb-4752-9cb5-1d7521b84607.xml, FltCheckAndGrowNameControl, FltCheckAndGrowNameControl routine [Installable File System Drivers], fltkernel/FltCheckAndGrowNameControl, ifsk.fltcheckandgrownamecontrol
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltCheckAndGrowNameControl
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltCheckAndGrowNameControl function
The <b>FltCheckAndGrowNameControl</b> routine checks whether the buffer in a <a href="..\fltkernel\ns-fltkernel-_flt_name_control.md">FLT_NAME_CONTROL</a> structure is large enough to hold the specified number of bytes. If not, <b>FltCheckAndGrowNameControl</b> replaces it with a larger system-allocated buffer.

## Syntax

````
NTSTATUS FltCheckAndGrowNameControl(
  _Inout_ PFLT_NAME_CONTROL NameCtrl,
  _In_    USHORT            NewSize
);
````

## Parameters

`NameCtrl`

Pointer to a <a href="..\fltkernel\ns-fltkernel-_flt_name_control.md">FLT_NAME_CONTROL</a> structure containing file name information.

`NewSize`

Required size, in bytes, of the new name control buffer.


## Return Value

<b>FltCheckAndGrowNameControl</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

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
There is insufficient memory in the free pool to satisfy the request. 

</td>
</tr>
</table>

## Remarks

Minifilter drivers must not attempt to free or replace the buffer in the <b>Name</b> member of a <a href="..\fltkernel\ns-fltkernel-_flt_name_control.md">FLT_NAME_CONTROL</a> structure directly. Instead, minifilter drivers should call <b>FltCheckAndGrowNameControl</b> to obtain a larger name buffer. 

If the size, in bytes, of the buffer in the <i>NameCtrl</i> structure is less than the value of the <i>NewSize</i> parameter, <b>FltCheckAndGrowNameControl</b> replaces it with a larger system-allocated buffer. <b>FltCheckAndGrowNameControl</b> copies the contents of the old buffer into the new one and frees the old buffer. 

If the size, in bytes, of the buffer in the <i>NameCtrl</i> structure is greater than or equal to the value of the <i>NewSize</i> parameter, <b>FltCheckAndGrowNameControl</b> returns STATUS_SUCCESS and does not replace the buffer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\fltkernel\ns-fltkernel-_flt_name_control.md">FLT_NAME_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543030">FltGetFileNameFormat</a>



<a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformation.md">FltGetFileNameInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformationunsafe.md">FltGetFileNameInformationUnsafe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543040">FltGetFileNameQueryMethod</a>