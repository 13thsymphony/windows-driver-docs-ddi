---
UID: NF:wdm.PoUnregisterSystemState
title: PoUnregisterSystemState function
author: windows-driver-content
description: The PoUnregisterSystemState routine cancels a system state registration created by PoRegisterSystemState.
old-location: kernel\pounregistersystemstate.htm
old-project: kernel
ms.assetid: 5d82342e-c800-44ac-8618-468355d14dd0
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: PoUnregisterSystemState, PoUnregisterSystemState routine [Kernel-Mode Driver Architecture], kernel.pounregistersystemstate, portn_b6118bd0-5fe1-4e75-8c17-e81d1f26814c.xml, wdm/PoUnregisterSystemState
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
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PoUnregisterSystemState
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# PoUnregisterSystemState function
The <b>PoUnregisterSystemState</b> routine cancels a system state registration created by <a href="..\wdm\nf-wdm-poregistersystemstate.md">PoRegisterSystemState</a>.

## Syntax

````
VOID PoUnregisterSystemState(
  _Inout_ PVOID StateHandle
);
````

## Parameters

`StateHandle`

A pointer to a handle previously returned by <b>PoRegisterSystemState</b>.


## Return Value

None

## Remarks

This routine cancels a system busy state registration established by <b>PoRegisterSystemState</b> and frees the associated <i>StateHandle</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<=APC_LEVEL" |

## See Also

<a href="..\wdm\nf-wdm-poregistersystemstate.md">PoRegisterSystemState</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoUnregisterSystemState routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>