---
UID : NF:ntifs.MmIsRecursiveIoFault
title : MmIsRecursiveIoFault function
author : windows-driver-content
description : The MmIsRecursiveIoFault routine determines whether the current page fault is occurring during an I/O operation.
old-location : ifsk\mmisrecursiveiofault.htm
old-project : ifsk
ms.assetid : c445c016-2781-4a82-ac2d-4c6eaff3b4c8
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : MmIsRecursiveIoFault
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : MmIsRecursiveIoFault
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
req.irql : <= DISPATCH_LEVEL
req.typenames : TOKEN_TYPE
---


# MmIsRecursiveIoFault function
The <b>MmIsRecursiveIoFault</b> routine determines whether the current page fault is occurring during an I/O operation.

## Syntax

````
BOOLEAN  MmIsRecursiveIoFault(
   VOID 
);
````

## Parameters

This function has no parameters.

## Return Value

<b>MmIsRecursiveIoFault</b> returns <b>TRUE</b> if a file system I/O operation is in progress for the current thread, <b>FALSE</b> otherwise.

## Remarks

When a page fault occurs, the file system can call <b>MmIsRecursiveIoFault</b> to determine whether an I/O operation is in progress for the current thread.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ntddk\nf-ntddk-mmisaddressvalid.md">MmIsAddressValid</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20MmIsRecursiveIoFault routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>