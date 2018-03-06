---
UID: NF:wdm.IoIsErrorUserInduced
title: IoIsErrorUserInduced macro
author: windows-driver-content
description: The IoIsErrorUserInduced routine determines whether an I/O error encountered while processing a request to a removable-media device was caused by the user.
old-location: kernel\ioiserroruserinduced.htm
old-project: kernel
ms.assetid: 6f5e54e8-c127-44d9-b1a6-e6f7ac3b3b51
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IoIsErrorUserInduced, IoIsErrorUserInduced routine [Kernel-Mode Driver Architecture], k104_860a6f10-e6c0-44cd-9386-c09e356f3472.xml, kernel.ioiserroruserinduced, wdm/IoIsErrorUserInduced
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: wdm.h
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	IoIsErrorUserInduced
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoIsErrorUserInduced function
The <b>IoIsErrorUserInduced</b> routine determines whether an I/O error encountered while processing a request to a removable-media device was caused by the user.

## Syntax

````
BOOLEAN IoIsErrorUserInduced(
  _In_ NTSTATUS Status
);
````

## Parameters

`Status`

Specifies the current NTSTATUS value, usually within the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff544079">DpcForIsr</a> routine.


## Return Value

None

## Remarks

This routine indicates whether an I/O request failed for one of the following user-correctable conditions:  

STATUS_DEVICE_NOT_READY

STATUS_IO_TIMEOUT

STATUS_MEDIA_WRITE_PROTECTED

STATUS_NO_MEDIA_IN_DEVICE

STATUS_UNRECOGNIZED_MEDIA

STATUS_VERIFY_REQUIRED

STATUS_WRONG_VOLUME

If <b>IoIsErrorUserInduced</b> returns <b>TRUE</b>, the removable-media driver must call <a href="..\ntddk\nf-ntddk-iosetharderrororverifydevice.md">IoSetHardErrorOrVerifyDevice</a> before completing the IRP.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | wdm.h |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\nf-wdm-iowriteerrorlogentry.md">IoWriteErrorLogEntry</a>



<a href="..\wdm\nf-wdm-ioallocateerrorlogentry.md">IoAllocateErrorLogEntry</a>



<a href="..\ntddk\nf-ntddk-iosetharderrororverifydevice.md">IoSetHardErrorOrVerifyDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoIsErrorUserInduced routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>