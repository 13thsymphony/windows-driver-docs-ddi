---
UID : NF:wdm.TmReadOnlyEnlistment
title : TmReadOnlyEnlistment function
author : windows-driver-content
description : The TmReadOnlyEnlistment routine sets a specified enlistment to be read-only.
old-location : kernel\tmreadonlyenlistment.htm
old-project : kernel
ms.assetid : 7d375152-c1d2-4e6d-a6a8-7394a7ef0e35
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : TmReadOnlyEnlistment
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
req.alt-api : TmReadOnlyEnlistment
req.alt-loc : NtosKrnl.exe,Ext-MS-Win-ntos-tm-l1-1-0.dll,tm.sys
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
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# TmReadOnlyEnlistment function
The <b>TmReadOnlyEnlistment</b> routine sets a specified enlistment to be read-only.

## Syntax

````
NTSTATUS TmReadOnlyEnlistment(
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

<b>TmReadOnlyEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 
<dl>
<dt><b>STATUS_TRANSACTION_NOT_REQUESTED</b></dt>
</dl>The transaction or its enlistment is not in the correct state. For example, an enlistment cannot be read-only if the ENLISTMENT_SUPERIOR flag was specified to <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>.

 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

## Remarks

The <b>TmReadOnlyEnlistment</b> routine is a pointer-based version of the <a href="..\wdm\nf-wdm-zwreadonlyenlistment.md">ZwReadOnlyEnlistment</a> routine.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.

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

<dl>
<dt>
<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-tmcreateenlistment.md">TmCreateEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwreadonlyenlistment.md">ZwReadOnlyEnlistment</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TmReadOnlyEnlistment routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>