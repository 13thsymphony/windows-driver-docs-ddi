---
UID : NF:ntifs.IoIsOperationSynchronous
title : IoIsOperationSynchronous function
author : windows-driver-content
description : The IoIsOperationSynchronous routine determines whether a given IRP represents a synchronous or asynchronous I/O request.
old-location : ifsk\ioisoperationsynchronous.htm
old-project : ifsk
ms.assetid : b233dfab-6a99-4f2f-930e-cafd01dc4bb5
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : IoIsOperationSynchronous
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
req.alt-api : IoIsOperationSynchronous
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
req.irql : Any level
req.typenames : TOKEN_TYPE
---


# IoIsOperationSynchronous function
The <b>IoIsOperationSynchronous</b> routine determines whether a given IRP represents a synchronous or asynchronous I/O request.

## Syntax

````
BOOLEAN IoIsOperationSynchronous(
  _In_ PIRP Irp
);
````

## Parameters

`Irp`

Pointer to the IRP for the operation.


## Return Value

<b>IoIsOperationSynchronous</b> returns <b>TRUE</b> if the operation is synchronous, otherwise <b>FALSE</b>.

## Remarks

<b>IoIsOperationSynchronous</b> determines whether a given IRP requests a synchronous or asynchronous I/O operation, according to the following conditions: 

If the IRP requests asynchronous paging I/O, the operation is asynchronous, even if one of the other conditions is true. 

If the IRP requests synchronous paging I/O, the operation is synchronous. 

If the file object was opened for synchronous I/O, the operation is synchronous. 

If the IRP_SYNCHRONOUS_API flag is set in the IRP, the operation is synchronous. This flag is set for operations, such as <a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a> and <a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>, that are always synchronous, even when performed on a file object that was opened for asynchronous I/O. 

If none of the above conditions is true, the operation is asynchronous.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-iobuildsynchronousfsdrequest.md">IoBuildSynchronousFsdRequest</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-iocreatefile.md">IoCreateFile</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-iocreatefileex.md">IoCreateFileEx</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-iocreatefilespecifydeviceobjecthint.md">IoCreateFileSpecifyDeviceObjectHint</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_irp.md">IRP</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwqueryinformationfile.md">ZwQueryInformationFile</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwsetinformationfile.md">ZwSetInformationFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoIsOperationSynchronous routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>