---
UID: NF:wdm.KeRaiseIrql
title: KeRaiseIrql macro
author: windows-driver-content
description: The KeRaiseIrql routine raises the hardware priority to the specified IRQL value, thereby masking off interrupts of equivalent or lower IRQL on the current processor.
old-location: kernel\keraiseirql.htm
old-project: kernel
ms.assetid: ee340d85-5a66-4773-b325-831257e9bfd8
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeRaiseIrql
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeRaiseIrql
req.alt-loc: Hal.lib,Hal.dll
req.ddi-compliance: IrqlKeRaiseLower, IrqlKeRaiseLower2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hal.lib
req.dll: 
req.irql: Any level (see Remarks section)
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeRaiseIrql macro



## -description
The <b>KeRaiseIrql</b> routine raises the hardware priority to the specified IRQL value, thereby masking off interrupts of equivalent or lower IRQL on the current processor.



## -syntax

````
VOID KeRaiseIrql(
  _In_  KIRQL  NewIrql,
  _Out_ PKIRQL OldIrql
);
````


## -parameters

### -param NewIrql [in]

Specifies the new IRQL to which the hardware priority is to be raised.


### -param OldIrql [out]

Pointer to the storage for the original (unraised) IRQL value to be used in a subsequent call to <a href="..\wdm\nf-wdm-kelowerirql.md">KeLowerIrql</a>.


## -remarks
If the new IRQL is less than the current IRQL, a bug check occurs. Otherwise, the current IRQL is set to the specified value.

Callers of this routine can be running at any IRQL. Any caller should restore the original IRQL with <a href="..\wdm\nf-wdm-kelowerirql.md">KeLowerIrql</a> as soon as possible.

A call to <b>KeLowerIrql</b> is valid if it specifies <i>NewIrql</i> &lt;= <i>CurrentIrql</i>. A call to <b>KeRaiseIrql</b> is valid if the caller specifies <i>NewIrql</i> &gt;= <i>CurrentIrql</i>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Hal.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level (see Remarks section)

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547817">IrqlKeRaiseLower</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547821">IrqlKeRaiseLower2</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-kegetcurrentirql.md">KeGetCurrentIrql</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kelowerirql.md">KeLowerIrql</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeRaiseIrql routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

