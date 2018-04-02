---
UID: NI:ks.IOCTL_KS_METHOD
title: IOCTL_KS_METHOD
author: windows-driver-content
description: An application can use IOCTL_KS_METHOD to execute a method on a KS object. The application passes IOCTL_KS_METHOD with the parameters described below to the KsSynchronousDeviceControl function.
old-location: stream\ioctl_ks_method.htm
old-project: stream
ms.assetid: a1b8c406-0d83-4145-b2cc-24e1f00ab80b
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IOCTL_KS_METHOD, IOCTL_KS_METHOD control code [Streaming Media Devices], ks-ioctl_4e1471f0-3763-4828-9186-7771de6201bd.xml, ks/IOCTL_KS_METHOD, stream.ioctl_ks_method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
api_name:
-	IOCTL_KS_METHOD
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_KS_METHOD IOCTL
An application can use IOCTL_KS_METHOD to execute a method on a KS object. The application passes IOCTL_KS_METHOD with the parameters described below to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567142">KsSynchronousDeviceControl</a> function.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The application places a pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a> specifying the method to invoke in the <b>InBuffer</b> parameter, and the size of the method structure at <b>InLength</b>.

### Input Buffer Length
The size of the method structure at <b>InLength</b>.

### Output Buffer
The client allocates and passes an output buffer if the method requires one. (This is determined by the flags set in the KSMETHOD structure.) For example, <a href="https://msdn.microsoft.com/library/windows/hardware/ff563428">KSMETHOD_STREAMALLOCATOR_ALLOC</a> provides an output buffer for the newly allocated frame.

### Output Buffer Length
Length of the output buffer.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the request is successful, the Status member is set to STATUS_SUCCESS.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561944">KSFASTMETHOD_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563420">KSMETHOD_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563423">KSMETHOD_SET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563399">KsMethodHandler</a>