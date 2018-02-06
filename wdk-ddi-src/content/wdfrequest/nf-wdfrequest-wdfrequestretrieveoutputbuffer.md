---
UID: NF:wdfrequest.WdfRequestRetrieveOutputBuffer
title: WdfRequestRetrieveOutputBuffer function
author: windows-driver-content
description: The WdfRequestRetrieveOutputBuffer method retrieves an I/O request's output buffer.
old-location: wdf\wdfrequestretrieveoutputbuffer.htm
old-project: wdf
ms.assetid: 5f12dd97-d8e7-4fef-91bf-00243c0cdd52
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfrequest/WdfRequestRetrieveOutputBuffer, kmdf.wdfrequestretrieveoutputbuffer, DFRequestObjectRef_05ab728b-3b70-4095-acca-294443797557.xml, WdfRequestRetrieveOutputBuffer, wdf.wdfrequestretrieveoutputbuffer, PFN_WDFREQUESTRETRIEVEOUTPUTBUFFER, WdfRequestRetrieveOutputBuffer method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: BufAfterReqCompletedIntIoctl, BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctl, BufAfterReqCompletedIoctlA, BufAfterReqCompletedRead, BufAfterReqCompletedReadA, BufAfterReqCompletedWrite, DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, OutputBufferAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfRequestRetrieveOutputBuffer
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---


# WdfRequestRetrieveOutputBuffer function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestRetrieveOutputBuffer</b> method retrieves an I/O request's output buffer.

## Syntax

````
NTSTATUS WdfRequestRetrieveOutputBuffer(
  _In_      WDFREQUEST Request,
  _In_      size_t     MinimumRequiredSize,
  _Out_     PVOID      *Buffer,
  _Out_opt_ size_t     *Length
);
````

## Parameters

`Request`

A handle to a framework request object.

`MinimumRequiredSize`

The minimum buffer size, in bytes, that the driver needs to process the I/O request.

`Buffer`

A pointer to a location that receives the buffer's address.

`Length`

A pointer to a location that receives the buffer's size, in bytes. This parameter is optional and can be <b>NULL</b>.


## Return Value

<b>WdfRequestRetrieveOutputBuffer</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An input parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The output buffer's length is zero, or the <i>MinimumRequiredSize</i> parameter specifies a buffer size that is larger than the buffer's actual size.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The request type is not valid or the request is using <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">neither buffered nor direct I/O</a>. For more information about supported methods for accessing data buffers, see the following Remarks section.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INTERNAL_ERROR</b></dt>
</dl>
</td>
<td width="60%">
The request has already been completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is insufficient memory.

</td>
</tr>
</table> 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.

## Remarks

A request's output buffer receives information, such as data from a disk, that the driver provides to the originator of the request. Your driver can call <b>WdfRequestRetrieveOutputBuffer</b> to obtain the output buffer for a read request or a device I/O control request, but not for a write request (because write requests do not provide output data).

The <b>WdfRequestRetrieveOutputBuffer</b> method retrieves the output buffer for I/O requests that use the <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">buffered I/O</a> method or the <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">direct I/O</a> method for accessing data buffers. If the request's I/O control code is <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>, or if the request came from another kernel-mode driver, <b>WdfRequestRetrieveOutputBuffer</b> also supports I/O requests that use <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">neither buffered nor direct I/O</a>. 

If <b>WdfRequestRetrieveOutputBuffer</b> returns STATUS_SUCCESS, the driver receives the address and, optionally, the size of the output buffer. 

The driver can access the retrieved buffer until it <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">completes the I/O request</a> that the <i>Request</i> parameter represents.

Instead of calling <b>WdfRequestRetrieveOutputBuffer</b>, the driver can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a>, which creates a framework memory object that represents the buffer.

For more information about <b>WdfRequestRetrieveOutputBuffer</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfrequest.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | BufAfterReqCompletedIntIoctl, BufAfterReqCompletedIntIoctlA, BufAfterReqCompletedIoctl, BufAfterReqCompletedIoctlA, BufAfterReqCompletedRead, BufAfterReqCompletedReadA, BufAfterReqCompletedWrite, DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, OutputBufferAPI |

## See Also

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputmemory.md">WdfRequestRetrieveOutputMemory</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveinputbuffer.md">WdfRequestRetrieveInputBuffer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestRetrieveOutputBuffer method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>