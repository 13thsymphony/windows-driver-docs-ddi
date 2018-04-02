---
UID: NI:ntddscsi.IOCTL_SCSI_MINIPORT_DIAGNOSTIC
title: IOCTL_SCSI_MINIPORT_DIAGNOSTIC
author: windows-driver-content
description: The IOCTL_SCSI_MINIPORT_DIAGNOSTIC control code is use to perform a diagnostic request to the Miniport.
old-location: storage\ioctl_scsi_miniport_diagnostic.htm
old-project: storage
ms.assetid: 79E89E4A-3B06-40FA-BFA6-598331C0A330
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_SCSI_MINIPORT_DIAGNOSTIC, IOCTL_SCSI_MINIPORT_DIAGNOSTIC control code [Storage Devices], ntddscsi/IOCTL_SCSI_MINIPORT_DIAGNOSTIC, storage.ioctl_scsi_miniport_diagnostic
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddscsi.h
req.include-header: 
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddscsi.h
api_name:
-	IOCTL_SCSI_MINIPORT_DIAGNOSTIC
product: Windows
targetos: Windows
req.typenames: MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE
---

# IOCTL_SCSI_MINIPORT_DIAGNOSTIC IOCTL
The <b>IOCTL_SCSI_MINIPORT_DIAGNOSTIC</b> 
   control code is use to perform a diagnostic request to the Miniport.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<text></text>

### Input Buffer Length
<text></text>

### Output Buffer
<text></text>

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).

## Remarks
To perform this operation, call the <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> 
   function with the following parameters.


<pre class="syntax">BOOL 
   WINAPI 
   DeviceIoControl( (HANDLE)       hDevice,         // handle to device
                    (DWORD)        IOCTL_SCSI_MINIPORT_DIAGNOSTIC, // dwIoControlCode
                    (LPDWORD)      lpInBuffer,      // input buffer
                    (DWORD)        nInBufferSize,   // size of input buffer
                    (LPDWORD)      lpOutBuffer,     // output buffer
                    (DWORD)        nOutBufferSize,  // size of output buffer
                    (LPDWORD)      lpBytesReturned, // number of bytes returned
                    (LPOVERLAPPED) lpOverlapped );  // OVERLAPPED structure</pre>



Parameters

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddscsi.h |

## See Also

<a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>



<a href="https://msdn.microsoft.com/1F2B15A6-7C05-4FBA-B54F-EEF013FF5739">STORAGE_DIAGNOSTIC_MP_REQUEST</a>