---
UID: NF:wdm.KeAreAllApcsDisabled
title: KeAreAllApcsDisabled function
author: windows-driver-content
description: The KeAreAllApcsDisabled routine indicates whether the calling thread is inside a guarded region or running at IRQL &gt;= APC_LEVEL, which disables all APC delivery.
old-location: kernel\keareallapcsdisabled.htm
old-project: kernel
ms.assetid: b4b57819-e2c9-4ac3-989e-c5e064f7487b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeAreAllApcsDisabled, KeAreAllApcsDisabled routine [Kernel-Mode Driver Architecture], k105_91675ec9-bef3-4ef8-9403-14999e018745.xml, kernel.keareallapcsdisabled, wdm/KeAreAllApcsDisabled
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeAreAllApcsDisabled
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeAreAllApcsDisabled function
The <b>KeAreAllApcsDisabled</b> routine indicates whether the calling thread is inside a guarded region or running at IRQL &gt;= APC_LEVEL, which disables all APC delivery.

## Syntax

````
BOOLEAN KeAreAllApcsDisabled(void);
````

## Parameters

This function has no parameters.

## Return Value

<b>KeAreAllApcsDisabled</b> returns <b>TRUE</b> if the calling thread is inside a guarded region or running at IRQL &gt;= APC_LEVEL, and <b>FALSE</b> otherwise.

## Remarks

A thread inside a guarded region or running at IRQL &gt;= APC_LEVEL has all APCs disabled, including special kernel APCs.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Server 2003 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-keareapcsdisabled.md">KeAreApcsDisabled</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeAreAllApcsDisabled routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>