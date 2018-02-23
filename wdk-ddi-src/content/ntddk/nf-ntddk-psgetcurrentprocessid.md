---
UID: NF:ntddk.PsGetCurrentProcessId
title: PsGetCurrentProcessId function
author: windows-driver-content
description: The PsGetCurrentProcessId routine identifies the current thread's process.
old-location: kernel\psgetcurrentprocessid.htm
old-project: kernel
ms.assetid: 9434f740-34c1-4244-813d-3fe9f1ead333
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PsGetCurrentProcessId routine [Kernel-Mode Driver Architecture], ntddk/PsGetCurrentProcessId, PsGetCurrentProcessId, kernel.psgetcurrentprocessid, k108_e38b09ef-d948-4eb9-bfdd-24b25ba55034.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	PsGetCurrentProcessId
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---


# PsGetCurrentProcessId function
The <b>PsGetCurrentProcessId</b> routine identifies the current thread's process.

## Syntax

````
HANDLE PsGetCurrentProcessId(void);
````

## Parameters

This function has no parameters.

## Return Value

<b>PsGetCurrentProcessId</b> returns the process ID of the current thread's process.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\ntddk\nf-ntddk-psgetcurrentthreadid.md">PsGetCurrentThreadId</a>



<a href="..\ntddk\nf-ntddk-pssetloadimagenotifyroutine.md">PsSetLoadImageNotifyRoutine</a>



<a href="..\ntifs\nf-ntifs-psgetcurrentthread.md">PsGetCurrentThread</a>



<a href="..\wdm\nf-wdm-psgetcurrentthread.md">PsGetCurrentThread</a>



<a href="..\ntddk\nf-ntddk-pssetcreateprocessnotifyroutine.md">PsSetCreateProcessNotifyRoutine</a>



<a href="..\wdm\nf-wdm-iogetcurrentprocess.md">IoGetCurrentProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsGetCurrentProcessId routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>