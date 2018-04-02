---
UID: NF:fltkernel.FltLoadFilter
title: FltLoadFilter function
author: windows-driver-content
description: The FltLoadFilter routine dynamically loads a minifilter driver into the currently running system.
old-location: ifsk\fltloadfilter.htm
old-project: ifsk
ms.assetid: aecf5f5f-c0b7-487a-9db0-d01212aef094
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_e_to_o_3cdd26c1-dc25-4fa0-8ea1-a1458742cd45.xml, FltLoadFilter, FltLoadFilter routine [Installable File System Drivers], fltkernel/FltLoadFilter, ifsk.fltloadfilter
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
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltLoadFilter
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltLoadFilter function
The <b>FltLoadFilter</b> routine dynamically loads a minifilter driver into the currently running system.

## Syntax

```
NTSTATUS FLTAPI FltLoadFilter(
  PCUNICODE_STRING FilterName
);
```

## Parameters

`FilterName`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure containing the service name for the minifilter driver.


## Return Value

<b>FltLoadFilter</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DRIVER_FAILED_PRIOR_UNLOAD</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver could not be loaded because a previous version of the driver is still in memory. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FAILED_DRIVER_ENTRY</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver's <b>DriverEntry</b> routine returned an NTSTATUS value that was not a success code. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_IMAGE_ALREADY_LOADED</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver is already running. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
No matching minifilter driver was found. This is an error code. 

</td>
</tr>
</table>

## Remarks

A minifilter driver that has a dependency on another minifilter driver can load that minifilter driver by calling <b>FltLoadFilter</b>. 

To unload the supporting minifilter driver, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544602">FltUnloadFilter</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544602">FltUnloadFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>