---
UID : NF:wdm.TmRequestOutcomeEnlistment
title : TmRequestOutcomeEnlistment function
author : windows-driver-content
description : The TmRequestOutcomeEnlistment routine asks KTM to try to provide an immediate outcome (commit or rollback) for the transaction that is associated with a specified enlistment.
old-location : kernel\tmrequestoutcomeenlistment.htm
old-project : kernel
ms.assetid : 1e58be94-7a10-4708-a658-9de28e26a465
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : TmRequestOutcomeEnlistment, ktm_ref_9be6bea7-eae4-4621-8155-f8a06285bb97.xml, kernel.tmrequestoutcomeenlistment, TmRequestOutcomeEnlistment routine [Kernel-Mode Driver Architecture], wdm/TmRequestOutcomeEnlistment
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows Vista and later operating system versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# TmRequestOutcomeEnlistment function
The <b>TmRequestOutcomeEnlistment</b> routine asks KTM to try to provide an immediate outcome (commit or rollback) for the transaction that is associated with a specified enlistment.

## Syntax

````
NTSTATUS TmRequestOutcomeEnlistment(
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

<b>TmRequestOutcomeEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return the following value: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_REQUEST_NOT_VALID</b></dt>
</dl>
</td>
<td width="60%">
The specified enlistment is a <a href="https://msdn.microsoft.com/6f6bf61a-fe53-47b5-9559-f76334969af8">superior enlistment</a>.

</td>
</tr>
</table> 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

## Remarks

The <b>TmRequestOutcomeEnlistment</b> routine asks KTM to try to provide an immediate outcome (result) for the transaction. A resource manager can call <b>TmRequestOutcomeEnlistment</b> after it has called <a href="..\wdm\nf-wdm-tmpreparecomplete.md">TmPrepareComplete</a> or <a href="..\wdm\nf-wdm-zwpreparecomplete.md">ZwPrepareComplete</a>, if it later discovers that it cannot wait for an outcome because, for example, a surprise-removal of the disk has occurred. KTM might be able to force a rollback if all resource managers have not finished their prepare operations.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of Zw<i>Xxx</i> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.

For more information about <b>TmCreateEnlistment</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542865">Creating a Resource Manager</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>

<a href="..\wdm\nf-wdm-zwpreparecomplete.md">ZwPrepareComplete</a>

<a href="..\wdm\nf-wdm-tmcreateenlistment.md">TmCreateEnlistment</a>

<a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a>

<a href="..\wdm\nf-wdm-tmpreparecomplete.md">TmPrepareComplete</a>

<a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TmRequestOutcomeEnlistment routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>