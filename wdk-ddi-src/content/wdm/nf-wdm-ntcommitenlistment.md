---
UID : NF:wdm.NtCommitEnlistment
title : NtCommitEnlistment function
author : windows-driver-content
description : The ZwCommitEnlistment routine initiates the commit operation for a specified enlistment's transaction.
old-location : kernel\zwcommitenlistment.htm
old-project : kernel
ms.assetid : 9c7f3e24-1d7c-450e-bbef-df0479911bc6
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : NtCommitEnlistment
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows Vista and later operating system versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : ZwCommitEnlistment,NtCommitEnlistment
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : PASSIVE_LEVEL
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# NtCommitEnlistment function
The <b>ZwCommitEnlistment</b> routine initiates the commit operation for a specified enlistment's transaction.

## Syntax

````
NTSTATUS ZwCommitEnlistment(
  _In_     HANDLE         EnlistmentHandle,
  _In_opt_ PLARGE_INTEGER TmVirtualClock
);
````

## Parameters

`EnlistmentHandle`

A handle to an <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a> that was obtained by a previous call to <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a> or <a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>. The object must represent a <a href="https://msdn.microsoft.com/6f6bf61a-fe53-47b5-9559-f76334969af8">superior enlistment</a> and the handle must have ENLISTMENT_SUPERIOR_RIGHTS access to the object.

`TmVirtualClock`

A pointer to a <a href="https://msdn.microsoft.com/de01b0f1-86b1-4e7d-af22-84dbbe3a3f83">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>.


## Return Value

<b>ZwCommitEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>The specified handle is not a handle to an enlistment object.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>The object handle is invalid.
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The caller does not have appropriate access to the enlistment object.
<dl>
<dt><b>STATUS_ENLISTMENT_NOT_SUPERIOR</b></dt>
</dl>The caller is not a <a href="https://msdn.microsoft.com/6f6bf61a-fe53-47b5-9559-f76334969af8">superior transaction manager</a> for the enlistment.
<dl>
<dt><b>STATUS_TRANSACTION_RESPONSE_NOT_ENLISTED</b></dt>
</dl>The caller did not register to receive TRANSACTION_NOTIFY_COMMIT_COMPLETE notifications.
<dl>
<dt><b>STATUS_TRANSACTION_REQUEST_NOT_VALID</b></dt>
</dl>The enlistment's transaction is not in a state that allows it to be committed.
<dl>
<dt><b>STATUS_TRANSACTION_NOT_ACTIVE</b></dt>
</dl>The commit operation for this transaction has already been started.
<dl>
<dt><b>STATUS_TRANSACTION_ALREADY_ABORTED</b></dt>
</dl>The transaction cannot be committed because it has been rolled back.

 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

## Remarks

Only superior transaction managers can call <b>ZwCommitEnlistment</b>.

Callers of <b>ZwCommitEnlistment</b> must register to receive TRANSACTION_NOTIFY_COMMIT_COMPLETE <a href="https://msdn.microsoft.com/library/windows/hardware/mt244308">notifications</a>.

The <b>ZwCommitEnlistment</b> routine causes KTM to send TRANSACTION_NOTIFY_COMMIT notifications to all resource managers that have enlisted in the transaction.

For more information about <b>ZwCommitEnlistment</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542870">Creating a Superior Transaction Manager</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff546783">Handling Commit Operations</a>.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-tmcommitenlistment.md">TmCommitEnlistment</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwCommitEnlistment routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>