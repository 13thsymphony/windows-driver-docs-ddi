---
UID: NF:wdm.KeDeregisterBoundCallback
title: KeDeregisterBoundCallback function
author: windows-driver-content
description: The KeDeregisterBoundCallback routine deregisters a user-mode bound exception callback registered by KeRegisterBoundCallback.
old-location: kernel\kederegisterboundcallback.htm
old-project: kernel
ms.assetid: 697709D4-DBB7-4CB4-83A1-89E8BAFD68DA
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeDeregisterBoundCallback, kernel.kederegisterboundcallback, wdm/KeDeregisterBoundCallback, KeDeregisterBoundCallback routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeDeregisterBoundCallback
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeDeregisterBoundCallback function
The <b>KeDeregisterBoundCallback</b> routine deregisters a user-mode bound exception callback registered by <a href="..\wdm\nf-wdm-keregisterboundcallback.md">KeRegisterBoundCallback</a>.

## Syntax

````
NTSTATUS KeDeregisterBoundCallback(
  _In_ PVOID Handle
);
````

## Parameters

`Handle`

Specifies the value returned by <a href="..\wdm\nf-wdm-keregisterboundcallback.md">KeRegisterBoundCallback</a> when the callback was registered.


## Return Value

The <b>KeDeregisterBoundCallback</b> routine returns STATUS_SUCCESS if the callback is successfully removed. It returns STATUS_INVALID_HANDLE if no callback matching the provided <i>Handle</i> value is found.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 10. Available starting with Windows 10. |
| **Target Platform** | Universal |
| **Header** | wdm.h |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |

## See Also

<a href="..\wdm\nf-wdm-keregisterboundcallback.md">KeRegisterBoundCallback</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeDeregisterBoundCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>