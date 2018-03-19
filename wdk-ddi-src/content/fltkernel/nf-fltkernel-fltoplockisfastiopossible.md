---
UID: NF:fltkernel.FltOplockIsFastIoPossible
title: FltOplockIsFastIoPossible function
author: windows-driver-content
description: The FltOplockIsFastIoPossible routine checks a file's opportunistic lock (oplock) state to determine whether fast I/O can be performed on the file.
old-location: ifsk\fltoplockisfastiopossible.htm
old-project: ifsk
ms.assetid: 0b1a4e61-9e1f-4469-b8d3-a3b75667ee7e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_e_to_o_d80a24fe-5ca7-43e6-8e6f-cb9414c427c3.xml, FltOplockIsFastIoPossible, FltOplockIsFastIoPossible routine [Installable File System Drivers], fltkernel/FltOplockIsFastIoPossible, ifsk.fltoplockisfastiopossible
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltOplockIsFastIoPossible
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltOplockIsFastIoPossible function
The <b>FltOplockIsFastIoPossible</b> routine checks a file's opportunistic lock (oplock) state to determine whether fast I/O can be performed on the file.

## Syntax

````
BOOLEAN FltOplockIsFastIoPossible(
  _In_ POPLOCK Oplock
);
````

## Parameters

`Oplock`

Opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>.


## Return Value

<b>FltOplockIsFastIoPossible</b> returns <b>FALSE</b> if there are outstanding oplocks on the file that prevent fast I/O from being performed; <b>TRUE</b> otherwise.

## Remarks

<b>FltOplockIsFastIoPossible</b> determines whether fast I/O can be performed on a file, according to the following conditions: 

<ul>
<li>
If the <i>Oplock</i> parameter is <b>NULL</b>, or if the value of *<i>Oplock</i> is <b>NULL</b>, there are no outstanding oplocks on the file, and fast I/O can be performed on the file. 

</li>
<li>
If an exclusive oplock was granted for the file, but no oplock break is in progress, fast I/O can be performed on the file. 

</li>
</ul>
For detailed information about opportunistic locks, see the Windows SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **DLL** | Fltmgr.sys |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="..\rxprocs\nf-rxprocs-fsrtloplockisfastiopossible.md">FsRtlOplockIsFastIoPossible</a>



<a href="..\fltkernel\nf-fltkernel-fltcheckoplock.md">FltCheckOplock</a>



<a href="..\fltkernel\nf-fltkernel-fltuninitializeoplock.md">FltUninitializeOplock</a>



<a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>



<a href="..\fltkernel\nf-fltkernel-fltcurrentbatchoplock.md">FltCurrentBatchOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="..\fltkernel\nf-fltkernel-fltoplockfsctrl.md">FltOplockFsctrl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>