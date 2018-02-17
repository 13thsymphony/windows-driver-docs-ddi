---
UID: NF:wdm.TmCommitComplete
title: TmCommitComplete function
author: windows-driver-content
description: The TmCommitComplete routine notifies KTM that the calling resource manager has finished committing a transaction.
old-location: kernel\tmcommitcomplete.htm
old-project: kernel
ms.assetid: a5f55966-98d9-42ec-9af6-254d2cb9a5bd
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: TmCommitComplete, wdm/TmCommitComplete, kernel.tmcommitcomplete, TmCommitComplete routine [Kernel-Mode Driver Architecture], ktm_ref_e6357c60-303b-4d42-a0a2-1ff3766acbb9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ext-MS-Win-ntos-tm-l1-1-0.dll
-	tm.sys
apiname:
-	TmCommitComplete
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# TmCommitComplete function
The <b>TmCommitComplete</b> routine notifies KTM that the calling  resource manager has finished committing a transaction.

## Syntax

````
NTSTATUS TmCommitComplete(
  _In_ PKENLISTMENT   Enlistment,
  _In_ PLARGE_INTEGER TmVirtualClock
);
````

## Parameters

`Enlistment`

A pointer to an <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a>. Your component can receive this pointer as input to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> callback routine. Alternatively, your component can call <a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>, <a href="..\wdm\nf-wdm-tmcreateenlistment.md">TmCreateEnlistment</a>, or <a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a> provided.

`TmVirtualClock`

A pointer to a <a href="https://msdn.microsoft.com/de01b0f1-86b1-4e7d-af22-84dbbe3a3f83">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>.


## Return Value

<b>TmCommitComplete</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_NOT_REQUESTED</b></dt>
</dl>
</td>
<td width="60%">
The transaction or its enlistment is not in the correct state.

</td>
</tr>
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

## Remarks

The <b>TmCommitComplete</b> routine is a pointer-based version of the <a href="..\wdm\nf-wdm-zwcommitcomplete.md">ZwCommitComplete</a> routine.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later operating system versions.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wdm\nf-wdm-zwcommitcomplete.md">ZwCommitComplete</a>



<a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>



<a href="..\wdm\nf-wdm-tmcreateenlistment.md">TmCreateEnlistment</a>



<a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>



<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TmCommitComplete routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>