---
UID: NF:wdm.ExReleaseRundownProtectionEx
title: ExReleaseRundownProtectionEx function
author: windows-driver-content
description: The ExReleaseRundownProtectionEx routine releases run-down protection that the caller previously acquired by calling the ExAcquireRundownProtectionEx routine.
old-location: kernel\exreleaserundownprotectionex.htm
old-project: kernel
ms.assetid: 9CF77F14-93E5-4742-A01C-770BC814507C
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: ExReleaseRundownProtectionEx, ExReleaseRundownProtectionEx routine [Kernel-Mode Driver Architecture], kernel.exreleaserundownprotectionex, wdm/ExReleaseRundownProtectionEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Server 2003.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExReleaseRundownProtectionEx
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ExReleaseRundownProtectionEx function
The <b>ExReleaseRundownProtectionEx</b> routine releases run-down protection that the caller previously acquired by calling the <a href="..\wdm\nf-wdm-exacquirerundownprotectionex.md">ExAcquireRundownProtectionEx</a> routine.

## Syntax

````
VOID ExReleaseRundownProtectionEx(
  _Inout_ PEX_RUNDOWN_REF RunRef,
  _In_    ULONG           Count
);
````

## Parameters

`RunRef`

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure that was initialized by a previous call to the  <a href="..\wdm\nf-wdm-exinitializerundownprotection.md">ExInitializeRundownProtection</a> routine. The run-down protection routines use this structure to track the run-down status of the associated shared object. This structure is opaque to drivers.

`Count`

The amount by which to decrement to the run-down instance count of the object. For more information, see Remarks.


## Return Value

None.

## Remarks

The <i>RunRef</i> parameter points to an <a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a> structure that tracks the run-down status of the associated object. This status information includes a count of the instances of run-down protection that are currently in effect on the object. The <a href="..\wdm\nf-wdm-exacquirerundownprotectionex.md">ExAcquireRundownProtectionEx</a> and <b>ExReleaseRundownProtectionEx</b> routines increment and decrement this count by arbitrary amounts. Two related routines,  <a href="..\wdm\nf-wdm-exacquirerundownprotection.md">ExAcquireRundownProtection</a> and <a href="..\wdm\nf-wdm-exreleaserundownprotection.md">ExReleaseRundownProtection</a>, increment and decrement this count by one.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj569382">Run-Down Protection</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Server 2003.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |
| **DDI compliance rules** | HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-exacquirerundownprotection.md">ExAcquireRundownProtection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj569379">EX_RUNDOWN_REF</a>



<a href="..\wdm\nf-wdm-exreleaserundownprotection.md">ExReleaseRundownProtection</a>



<a href="..\wdm\nf-wdm-exacquirerundownprotectionex.md">ExAcquireRundownProtectionEx</a>



<a href="..\wdm\nf-wdm-exinitializerundownprotection.md">ExInitializeRundownProtection</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExReleaseRundownProtectionEx routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>