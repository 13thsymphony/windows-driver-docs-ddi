---
UID: NF:ntifs.PsIsSystemThread
title: PsIsSystemThread function
author: windows-driver-content
description: The PsIsSystemThread routine checks whether a given thread is a system thread.
old-location: kernel\psissystemthread.htm
old-project: kernel
ms.assetid: ecbea013-b876-4690-a455-ebe420a4f050
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PsIsSystemThread, PsIsSystemThread routine [Kernel-Mode Driver Architecture], k108_eacaf1ad-4ab8-49a6-9d43-3aba7821e110.xml, kernel.psissystemthread, ntifs/PsIsSystemThread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsIsSystemThread
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# PsIsSystemThread function
The <b>PsIsSystemThread</b> routine checks whether a given thread is a system thread.

## Syntax

````
BOOLEAN PsIsSystemThread(
  _In_ PETHREAD Thread
);
````

## Parameters

`Thread`

Pointer to the thread to be checked.


## Return Value

<b>PsIsSystemThread</b> returns <b>TRUE</b> if the specified thread is a system thread, <b>FALSE</b> otherwise.

## Remarks

For more information about using system threads and managing synchronization within a nonarbitrary thread context, see <a href="https://msdn.microsoft.com/fbd8aadd-5a24-48c9-9865-80cc7dc97316">Driver Threads, Dispatcher Objects, and Resources</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\wdm\nf-wdm-psgetcurrentthread.md">PsGetCurrentThread</a>



<a href="..\ntifs\nf-ntifs-ioissystemthread.md">IoIsSystemThread</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsIsSystemThread routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>