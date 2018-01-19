---
UID : NF:wdm.KeRegisterBoundCallback
title : KeRegisterBoundCallback function
author : windows-driver-content
description : The KeRegisterBoundCallback routine registers a routine to be called whenever a user-mode bound exception occurs.
old-location : kernel\keregisterboundcallback.htm
old-project : kernel
ms.assetid : 0985589E-074A-45C8-9F8A-384DC42EC884
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : KeRegisterBoundCallback
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : 
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 10.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KeRegisterBoundCallback
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : 
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# KeRegisterBoundCallback function
The <b>KeRegisterBoundCallback</b> routine registers a routine to be called whenever a user-mode bound exception occurs.

## Syntax

````
PVOID KeRegisterBoundCallback(
  _In_ PBOUND_CALLBACK CallbackRoutine
);
````

## Parameters

`CallbackRoutine`

Pointer to a <a href="..\wdm\nc-wdm-bound_callback.md">BoundCallback</a> function.


## Return Value

On success, <b>KeRegisterBoundCallback</b> returns an opaque pointer that the caller passes to <a href="..\wdm\nf-wdm-kederegisterboundcallback.md">KeDeregisterBoundCallback</a> to deregister the callback. The routine returns <b>NULL</b> if it is unable to register the callback.

## Remarks

The <b>KeRegisterBoundCallback</b> routine provides the opportunity for a kernel-mode driver to intercept and handle user-mode bound exceptions. When a bounds exception for a user-mode thread occurs, the system calls the registered  <a href="..\wdm\nc-wdm-bound_callback.md">BoundCallback</a> function to manage the bounds trap. The return value of the <i>BoundCallback</i> function indicates the action that the system should then perform, such as propagating the bounds exception or terminating the user-mode process.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-kederegisterboundcallback.md">KeDeregisterBoundCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeRegisterBoundCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>