---
UID: NF:ntifs.ObIsKernelHandle
title: ObIsKernelHandle function
author: windows-driver-content
description: The ObIsKernelHandle routine determines whether the specified handle is a kernel handle.
old-location: ifsk\obiskernelhandle.htm
old-project: ifsk
ms.assetid: 8ebc3b7f-5b4b-4e92-95fe-1918b51d27ad
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ObIsKernelHandle, ObIsKernelHandle routine [Installable File System Drivers], ifsk.obiskernelhandle, ntifs/ObIsKernelHandle, obref_e80e117f-6001-4c6d-980c-413e538f3bb2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h, FltKernel.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ObIsKernelHandle
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# ObIsKernelHandle function
The <b>ObIsKernelHandle</b> routine determines whether the specified handle is a kernel handle.

## Syntax

````
BOOLEAN ObIsKernelHandle(
  _In_ HANDLE Handle
);
````

## Parameters

`Handle`

The handle to check.


## Return Value

<b>ObIsKernelHandle</b> returns <b>TRUE</b> if <i>Handle</i> is a kernel handle and <b>FALSE</b> otherwise.

## Remarks

You can use kernel handles only in kernel mode.  A driver can mark a handle as a kernel handle by specifying the OBJ_KERNEL_HANDLE flag in <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> when it creates the handle.

<div class="alert"><b>Note</b>  <b>ObIsKernelHandle</b> does not verify that the parameter is a valid handle.  This routine only determines if a valid handle is a kernel handle.  If the parameter is not a valid handle, the result of the routine is undefined.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include FltKernel.h, Ntifs.h, FltKernel.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a>