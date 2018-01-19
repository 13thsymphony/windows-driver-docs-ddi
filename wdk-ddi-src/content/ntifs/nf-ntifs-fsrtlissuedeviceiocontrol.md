---
UID : NF:ntifs.FsRtlIssueDeviceIoControl
title : FsRtlIssueDeviceIoControl function
author : windows-driver-content
description : The FsRtlIssueDeviceIoControl routine sends a synchronous device I/O control request to a target device object.
old-location : ifsk\fsrtlissuedeviceiocontrol.htm
old-project : ifsk
ms.assetid : 3BB31389-EB1B-4443-9FCF-70B420D71126
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : FsRtlIssueDeviceIoControl
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FsRtlIssueDeviceIoControl
req.alt-loc : ntoskrnl.lib,ntoskrnl.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ntoskrnl.lib
req.dll : 
req.irql : <= APC_LEVEL
req.typenames : TOKEN_TYPE
---


# FsRtlIssueDeviceIoControl function
The <b>FsRtlIssueDeviceIoControl</b> routine sends a synchronous device I/O control request to a target device object.

## Syntax

````
NTSTATUS FsRtlIssueDeviceIoControl(
  _In_      PDEVICE_OBJECT DeviceObject,
  _In_      ULONG          IoCtl,
  _In_      ULONG          IrpFlags,
  _In_opt_  ULONG          InputBuffer,
  _In_      ULONG          InputBufferLength,
  _Out_opt_ ULONG          OutputBuffer,
  _In_      ULONG          OutputBufferLength,
  _In_      PULONG_PTR     IosbInformation
);
````

## Parameters

`DeviceObject`

The target device object.

`IoCtl`

The IOCTL control code to issue.

`Flags`



`InputBuffer`

An optional buffer containing the input data for the request.

`InputBufferLength`

The length, in bytes, of the input data in <i>InputBuffer</i>.

`OutputBuffer`

An optional caller-supplied output buffer for returned data.

`OutputBufferLength`

The length, in bytes, of the output data buffer at <i>OutputBuffer</i>.

`IosbInformation`

A pointer to a <b>ULONG</b> status value to receive the information field value set in the I/O status block at completion of the request.


## Return Value

<b>FsRtlIssueDeviceIoControl</b> returns <b>STATUS_SUCCESS</b> or an another <b>NTSTATUS</b> value returned in the status block from the I/O operation.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltdeviceiocontrolfile.md">FltDeviceIoControlFile</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlIssueDeviceIoControl routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>