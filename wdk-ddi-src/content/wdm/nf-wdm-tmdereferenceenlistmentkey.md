---
UID : NF:wdm.TmDereferenceEnlistmentKey
title : TmDereferenceEnlistmentKey function
author : windows-driver-content
description : The TmDereferenceEnlistmentKey routine decrements the reference count for the key of a specified enlistment object.
old-location : kernel\tmdereferenceenlistmentkey.htm
old-project : kernel
ms.assetid : e03b5f4d-58d5-43d5-a0c3-8a3cc83bd38a
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : TmDereferenceEnlistmentKey routine [Kernel-Mode Driver Architecture], TmDereferenceEnlistmentKey, kernel.tmdereferenceenlistmentkey, wdm/TmDereferenceEnlistmentKey, ktm_ref_88254e83-cb2a-4da1-9216-b12314ea73ea.xml
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
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# TmDereferenceEnlistmentKey function
The <b>TmDereferenceEnlistmentKey</b> routine decrements the reference count for the key of a specified <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a>.

## Syntax

````
NTSTATUS TmDereferenceEnlistmentKey(
  _In_      PKENLISTMENT Enlistment,
  _Out_opt_ PBOOLEAN     LastReference
);
````

## Parameters

`Enlistment`

A pointer to an enlistment object. Your component can receive this pointer as input to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> callback routine. Alternatively, your component can call <a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>, <a href="..\wdm\nf-wdm-tmcreateenlistment.md">TmCreateEnlistment</a>, or <a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a> provided.

`LastReference`

A pointer to a BOOLEAN-typed variable. This variable receives <b>TRUE</b> if the reference count is zero after <b>TmDereferenceEnlistmentKey</b> decrements it. Otherwise, the variable receives <b>FALSE</b>.


## Return Value

<b>TmDereferenceEnlistmentKey</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The reference count of the specified enlistment object is zero and cannot be decremented.

</td>
</tr>
</table> 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

## Remarks

The <a href="..\wdm\nf-wdm-tmreferenceenlistmentkey.md">TmReferenceEnlistmentKey</a> routine increments the reference count for an enlistment object's key, and the <b>TmDereferenceEnlistmentKey</b> routine decrements the count.

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
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-tmcreateenlistment.md">TmCreateEnlistment</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a>

<a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>

<a href="..\wdm\nf-wdm-tmreferenceenlistmentkey.md">TmReferenceEnlistmentKey</a>

<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>

<a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TmDereferenceEnlistmentKey routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>