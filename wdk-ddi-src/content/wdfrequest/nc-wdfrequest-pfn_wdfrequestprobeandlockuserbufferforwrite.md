---
UID: NC:wdfrequest.PFN_WDFREQUESTPROBEANDLOCKUSERBUFFERFORWRITE
title: PFN_WDFREQUESTPROBEANDLOCKUSERBUFFERFORWRITE function
author: windows-driver-content
description: The WdfRequestProbeAndLockUserBufferForWrite method verifies that an I/O request's user-mode buffer is writeable, and then it locks the buffer's physical memory pages so drivers in the driver stack can write into the buffer.
old-location: wdf\wdfrequestprobeandlockuserbufferforwrite.htm
old-project: wdf
ms.assetid: a4e6f0aa-bf96-4274-9a1d-f37dc7bd96fd
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFREQUESTPROBEANDLOCKUSERBUFFERFORWRITE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfRequestProbeAndLockUserBufferForWrite
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PWDF_QUERY_INTERFACE_CONFIG, WDF_QUERY_INTERFACE_CONFIG
req.product: Windows 10 or later.
---

# PFN_WDFREQUESTPROBEANDLOCKUSERBUFFERFORWRITE function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfRequestProbeAndLockUserBufferForWrite</b> method verifies that an I/O request's user-mode buffer is writeable, and then it locks the buffer's physical memory pages so drivers in the driver stack can write into the buffer.



## -syntax

````
NTSTATUS WdfRequestProbeAndLockUserBufferForWrite(
  _In_  WDFREQUEST Request,
  _In_  PVOID      Buffer,
  _In_  size_t     Length,
  _Out_ WDFMEMORY  *MemoryObject
);
````


## -parameters

### -param Request [in]

A handle to a framework request object. 


### -param Buffer [in]

A pointer to the request's output buffer. For more information, see the following Remarks section.


### -param Length [in]

The length, in bytes, of the request's output buffer.


### -param MemoryObject [out]

A pointer to a location that receives a handle to a framework memory object that represents the user output buffer.


## -returns
<b>WdfRequestProbeAndLockUserBufferForWrite</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An input parameter is invalid.
<dl>
<dt><b>STATUS_INVALID_USER_BUFFER</b></dt>
</dl>The <i>Length</i> parameter is zero.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The request has already been completed or is otherwise invalid.
<dl>
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
</dl>The current thread is not the creator of the I/O request.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>There is insufficient memory to complete the operation.

 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




A bug check occurs if the driver supplies an invalid object handle.


## -remarks
The user output buffer typically receives information that the driver has read from the device.

Only a top-level driver can call the <b>WdfRequestProbeAndLockUserBufferForWrite</b> method, because the method requires the process context of the process that created the I/O request.

The user-mode buffer that the <i>Buffer</i> parameter specifies can be the buffer that <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveunsafeuseroutputbuffer.md">WdfRequestRetrieveUnsafeUserOutputBuffer</a> retrieves, or it can be a different user-mode output buffer. For example, an I/O control code that uses the buffered access method might pass a structure that contains an embedded pointer to a user-mode buffer. In such a case, the driver can use<b>WdfRequestProbeAndLockUserBufferForWrite</b> to obtain a memory object for the buffer. 

The buffer length that the <i>Length</i> parameter specifies must not be larger than the buffer's actual size. Otherwise, drivers can access memory outside of the buffer, which is a security risk.

If <b>WdfRequestProbeAndLockUserBufferForWrite</b> returns STATUS_SUCCESS, the driver receives a handle to a framework memory object that represents the user-mode buffer. To access the buffer, the driver must call <a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a>.

For more information about <b>WdfRequestProbeAndLockUserBufferForWrite</b>, see <a href="wdf.accessing_data_buffers_in_kmdf_drivers">Accessing Data Buffers in Framework-Based Drivers</a>.

For a code example that uses <b>WdfRequestProbeAndLockUserBufferForWrite</b>, see <a href="..\wdfrequest\nf-wdfrequest-wdfrequestprobeandlockuserbufferforread.md">WdfRequestProbeAndLockUserBufferForRead</a>.


## -see-also
<dl>
<dt>
<a href="..\wdfmemory\nf-wdfmemory-wdfmemorygetbuffer.md">WdfMemoryGetBuffer</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestprobeandlockuserbufferforread.md">WdfRequestProbeAndLockUserBufferForRead</a>
</dt>
<dt>
<a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveunsafeuseroutputbuffer.md">WdfRequestRetrieveUnsafeUserOutputBuffer</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestProbeAndLockUserBufferForWrite method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

