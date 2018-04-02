---
UID: NF:fltkernel.FltGetVolumeFromFileObject
title: FltGetVolumeFromFileObject function
author: windows-driver-content
description: The FltGetVolumeFromFileObject routine returns an opaque pointer for the volume that a given file stream resides on.
old-location: ifsk\fltgetvolumefromfileobject.htm
old-project: ifsk
ms.assetid: 3b13c4a2-b2b5-4b59-881c-01ee430ac720
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_e_to_o_9ad19df2-2e65-454b-9193-ce409153786a.xml, FltGetVolumeFromFileObject, FltGetVolumeFromFileObject routine [Installable File System Drivers], fltkernel/FltGetVolumeFromFileObject, ifsk.fltgetvolumefromfileobject
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetVolumeFromFileObject
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltGetVolumeFromFileObject function
The <b>FltGetVolumeFromFileObject</b> routine returns an opaque pointer for the volume that a given file stream resides on.

## Syntax

```
NTSTATUS FLTAPI FltGetVolumeFromFileObject(
  PFLT_FILTER  Filter,
  PFILE_OBJECT FileObject,
  PFLT_VOLUME  *RetVolume
);
```

## Parameters

`Filter`

Opaque filter pointer for the caller. This parameter is required and cannot be <b>NULL</b>.

`FileObject`

File object pointer for a file stream that resides on the volume.

`RetVolume`

Pointer to a caller-allocated variable that receives an opaque pointer for the volume. This parameter is required and cannot be <b>NULL</b>.


## Return Value

<b>FltGetVolumeFromFileObject</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The volume is being torn down. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
No matching volume was found. This is an error code. 

</td>
</tr>
</table>

## Remarks

<b>FltGetVolumeFromFileObject</b> adds a rundown reference to the opaque volume pointer returned in the <i>RetVolume</i> parameter. When this pointer is no longer needed, the caller must release it by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543378">FltObjectDereference</a>. Thus every successful call to <b>FltGetVolumeFromFileObject</b> must be matched by a subsequent call to <b>FltObjectDereference</b>. 

To get a pointer to the device object for a given volume, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543007">FltGetDeviceObject</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543007">FltGetDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543013">FltGetDiskDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543197">FltGetVolumeFromDeviceObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543378">FltObjectDereference</a>