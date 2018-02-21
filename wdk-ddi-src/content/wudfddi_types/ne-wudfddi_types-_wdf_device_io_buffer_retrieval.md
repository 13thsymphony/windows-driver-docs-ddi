---
UID: NE:wudfddi_types._WDF_DEVICE_IO_BUFFER_RETRIEVAL
title: "_WDF_DEVICE_IO_BUFFER_RETRIEVAL"
author: windows-driver-content
description: The WDF_DEVICE_IO_BUFFER_RETRIEVAL enumeration is used to specify when UMDF makes an I/O request's buffers available to the driver.
old-location: wdf\wdf_device_io_buffer_retrieval.htm
old-project: wdf
ms.assetid: 50ece9a1-8d0d-442c-962c-488bd6368a67
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wudfddi_types/WdfDeviceIoBufferRetrievalInvalid, *PWDF_DEVICE_IO_BUFFER_RETRIEVAL, WDF_DEVICE_IO_BUFFER_RETRIEVAL, wdf.wdf_device_io_buffer_retrieval, PWDF_DEVICE_IO_BUFFER_RETRIEVAL enumeration pointer, WdfDeviceIoBufferRetrievalMaximum, _WDF_DEVICE_IO_BUFFER_RETRIEVAL, WdfDeviceIoBufferRetrievalDeferred, umdfstructs_7bb0e71c-fbce-4f29-9373-a80527403e04.xml, WdfDeviceIoBufferRetrievalInvalid, wudfddi_types/WdfDeviceIoBufferRetrievalCopyImmediately, WDF_DEVICE_IO_BUFFER_RETRIEVAL enumeration, wudfddi_types/WdfDeviceIoBufferRetrievalMaximum, WdfDeviceIoBufferRetrievalCopyImmediately, PWDF_DEVICE_IO_BUFFER_RETRIEVAL, umdf.wdf_device_io_buffer_retrieval, wudfddi_types/WdfDeviceIoBufferRetrievalDeferred, wudfddi_types/WDF_DEVICE_IO_BUFFER_RETRIEVAL, wudfddi_types/PWDF_DEVICE_IO_BUFFER_RETRIEVAL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wudfddi_types.h
apiname:
-	WDF_DEVICE_IO_BUFFER_RETRIEVAL
product: Windows
targetos: Windows
req.typenames: "*PWDF_DEVICE_IO_BUFFER_RETRIEVAL, WDF_DEVICE_IO_BUFFER_RETRIEVAL"
req.product: Windows 10 or later.
---

# _WDF_DEVICE_IO_BUFFER_RETRIEVAL Enumeration
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WDF_DEVICE_IO_BUFFER_RETRIEVAL</b> enumeration is used to specify when UMDF makes an I/O request's buffers available to the driver.

## Syntax
````
typedef enum _WDF_DEVICE_IO_BUFFER_RETRIEVAL { 
  WdfDeviceIoBufferRetrievalInvalid          = 0x00,
  WdfDeviceIoBufferRetrievalCopyImmediately  = 0x01,
  WdfDeviceIoBufferRetrievalDeferred         = 0x02,
  WdfDeviceIoBufferRetrievalMaximum          = 0x3
} WDF_DEVICE_IO_BUFFER_RETRIEVAL, *PWDF_DEVICE_IO_BUFFER_RETRIEVAL;
````

## Constants

<table>
            
                <tr>
                    <td>WdfDeviceIoBufferRetrievalCopyImmediately</td>
                    <td>UMDF makes an I/O request's buffers available to the driver (by copying them into the <a href="https://msdn.microsoft.com/8b469c91-d33d-4fb0-8c7d-e90f86a1e339">UMDF driver host process</a>) as soon as UMDF receives the I/O request. For more information, see the following Remarks section.</td>
                </tr>
            
                <tr>
                    <td>WdfDeviceIoBufferRetrievalDeferred</td>
                    <td>UMDF makes an I/O request's buffers available to the driver (by copying them into the UMDF driver host process) only when the driver attempts to access the buffers. For more information, see the following Remarks section.</td>
                </tr>
            
                <tr>
                    <td>WdfDeviceIoBufferRetrievalInvalid</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>WdfDeviceIoBufferRetrievalMaximum</td>
                    <td>Reserved for system use.</td>
                </tr>
</table>

## Remarks

The <b>WDF_DEVICE_IO_BUFFER_RETRIEVAL</b> enumeration is used as input to <a href="https://msdn.microsoft.com/library/windows/hardware/ff556969">IWDFDeviceInitialize2::SetIoTypePreference</a>.

In UMDF versions prior to version 1.9, UMDF always makes an I/O request's buffers available to the driver (by copying the buffers into the <a href="https://msdn.microsoft.com/8b469c91-d33d-4fb0-8c7d-e90f86a1e339">UMDF driver host process</a>) as soon as UMDF receives the I/O request. <a href="https://msdn.microsoft.com/library/windows/hardware/ff559100">IWDFIoRequest::GetInputMemory</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff559112">IWDFIoRequest::GetOutputMemory</a> are the only object methods that drivers can call to access the buffers.

UMDF versions 1.9 and later can support either immediate or deferred retrieval of request buffers. All new drivers should enable deferred retrieval because it usually provides better driver performance than immediate retrieval. If a driver does not enable deferred retrieval, UMDF uses immediate retrieval.

To defer retrieval of buffers, your driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff556969">IWDFDeviceInitialize2::SetIoTypePreference</a> and specify the <b>WdfDeviceIoBufferRetrievalDeferred</b> value. After your driver enables deferred retrieval, it can call the following methods to access request buffers, using either the buffered or direct <a href="https://msdn.microsoft.com/f95a0aec-65f9-44c9-8ae5-11bb4d832752">access method</a>:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff559033">IWDFIoRequest2::RetrieveInputBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559037">IWDFIoRequest2::RetrieveInputMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559041">IWDFIoRequest2::RetrieveOutputBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559046">IWDFIoRequest2::RetrieveOutputMemory</a>


A driver that enables deferred retrieval cannot use <a href="https://msdn.microsoft.com/library/windows/hardware/ff559100">IWDFIoRequest::GetInputMemory</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff559112">IWDFIoRequest::GetOutputMemory</a> to access the buffers.

For more information about accessing an I/O request's data buffers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in UMDF-Based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum UMDF version** | 1.9 |
| **Header** | wudfddi_types.h (include Wudfddi.h) |

## See Also

<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_device_io_type.md">WDF_DEVICE_IO_TYPE (UMDF)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_IO_BUFFER_RETRIEVAL enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>