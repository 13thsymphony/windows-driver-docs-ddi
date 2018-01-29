---
UID : NF:wudfddi.IWDFIoRequest2.RetrieveOutputBuffer
title : IWDFIoRequest2::RetrieveOutputBuffer method
author : windows-driver-content
description : The RequestRetrieveOutputBuffer method retrieves an I/O request's output buffer.
old-location : wdf\iwdfiorequest2_retrieveoutputbuffer.htm
old-project : wdf
ms.assetid : c2c96663-df1b-4310-b51e-177e353bb059
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wudfddi/IWDFIoRequest2::RetrieveOutputBuffer, RetrieveOutputBuffer method, UMDFRequestObjectRef_895f34da-95f3-4256-a049-0221887da5e1.xml, wdf.iwdfiorequest2_retrieveoutputbuffer, umdf.iwdfiorequest2_retrieveoutputbuffer, RetrieveOutputBuffer, IWDFIoRequest2, RetrieveOutputBuffer method, IWDFIoRequest2 interface, IWDFIoRequest2 interface, RetrieveOutputBuffer method, IWDFIoRequest2::RetrieveOutputBuffer
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wudfddi.h
req.include-header : Wudfddi.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.9
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : wudfddi.h
req.dll : WUDFx.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPOWER_ACTION, POWER_ACTION"
req.product : Windows 10 or later.
---


# RetrieveOutputBuffer method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputbuffer.md">RequestRetrieveOutputBuffer</a> method retrieves an I/O request's output buffer.

## Syntax

````
HRESULT RetrieveOutputBuffer(
  [in]            SIZE_T MinimumRequiredCb,
  [out]           PVOID  *Buffer,
  [out, optional] SIZE_T *BufferCb
);
````

## Parameters

`MinimumRequiredCb`

The minimum buffer size, in bytes, that the driver needs to process the I/O request. This value can be zero if there is no minimum buffer size.

`Buffer`

A pointer to a location that receives the buffer's address.

`BufferCb`

A pointer to a location that receives the buffer's size, in bytes. This parameter is optional and can be <b>NULL</b>.


## Return Value

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputbuffer.md">RequestRetrieveOutputBuffer</a> returns S_OK if the operation succeeds. Otherwise, this method can return the following value:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</b></dt>
</dl>
</td>
<td width="60%">
The I/O request did not provide an output buffer, or the size of the output buffer is less than the minimum size that <i>MinimumRequiredCb</i> specifies.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
Not enough memory is available to retrieve the buffer. The driver should complete the request with an error status value.

</td>
</tr>
</table> 

This method might return one of the other values that Winerror.h contains.

## Remarks

A request's output buffer receives information, such as data from a disk, that the driver provides to the originator of the request. Your driver can call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputbuffer.md">RequestRetrieveOutputBuffer</a> to obtain the output buffer for a read request or a device I/O control request, but not for a write request (because write requests do not provide output data).

The <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputbuffer.md">RequestRetrieveOutputBuffer</a> method retrieves the output buffer for I/O requests that use the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">buffered I/O</a> or <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">direct I/O</a> method for accessing data buffers.

If <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputbuffer.md">RequestRetrieveOutputBuffer</a> returns S_OK, the driver receives the address and, optionally, the size of the output buffer. 

The driver can access the retrieved buffer until it <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">completes</a> the I/O request.

Instead of calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveoutputbuffer.md">RequestRetrieveOutputBuffer</a>, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559046">IWDFIoRequest2::RetrieveOutputMemory</a>, which creates a framework memory object that represents the buffer.

For more information about accessing an I/O request's data buffers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in UMDF-Based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** | 1.9 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559033">IWDFIoRequest2::RetrieveInputBuffer</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559100">IWDFIoRequest::GetInputMemory</a>

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559112">IWDFIoRequest::GetOutputMemory</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559037">IWDFIoRequest2::RetrieveInputMemory</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559046">IWDFIoRequest2::RetrieveOutputMemory</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest2::RetrieveOutputBuffer method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>