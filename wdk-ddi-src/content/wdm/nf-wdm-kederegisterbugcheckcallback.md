---
UID: NF:wdm.KeDeregisterBugCheckCallback
title: KeDeregisterBugCheckCallback function
author: windows-driver-content
description: The KeDeregisterBugCheckCallback routine removes a callback routine that was registered by KeRegisterBugCheckCallback.
old-location: kernel\kederegisterbugcheckcallback.htm
old-project: kernel
ms.assetid: 0be95cee-c648-4905-9f4a-ea4e5fc794ed
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.kederegisterbugcheckcallback, wdm/KeDeregisterBugCheckCallback, KeDeregisterBugCheckCallback routine [Kernel-Mode Driver Architecture], k105_6bb11ae2-ceb1-4640-b59c-47b42496b819.xml, KeDeregisterBugCheckCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
-	KeDeregisterBugCheckCallback
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeDeregisterBugCheckCallback function
The <b>KeDeregisterBugCheckCallback</b> routine removes a callback routine that was registered by <a href="..\wdm\nf-wdm-keregisterbugcheckcallback.md">KeRegisterBugCheckCallback</a>.

## Syntax

````
BOOLEAN KeDeregisterBugCheckCallback(
  _Inout_ PKBUGCHECK_CALLBACK_RECORD CallbackRecord
);
````

## Parameters

`CallbackRecord`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551853">KBUGCHECK_CALLBACK_RECORD</a> structure. <i>CallbackRecord</i> must be the same value that was passed to <a href="..\wdm\nf-wdm-keregisterbugcheckcallback.md">KeRegisterBugCheckCallback</a> when the callback was registered.


## Return Value

<b>KeDeregisterBugCheckCallback</b> returns <b>TRUE</b> if the specified callback is successfully removed. It returns <b>FALSE</b> if the specified callback is not registered.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\nf-wdm-keregisterbugcheckcallback.md">KeRegisterBugCheckCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeDeregisterBugCheckCallback routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>