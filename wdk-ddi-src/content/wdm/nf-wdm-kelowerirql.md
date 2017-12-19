---
UID: NF.wdm.KeLowerIrql
title: KeLowerIrql function
author: windows-driver-content
description: The KeLowerIrql routine restores the IRQL on the current processor to its original value.
old-location: kernel\kelowerirql.htm
old-project: kernel
ms.assetid: 95598654-71dd-41cc-a663-b0bcaee77687
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: KeLowerIrql
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
req.alt-api: KeLowerIrql
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
req.irql: Any level
req.product: Windows 10 or later.
---

# KeLowerIrql function



## -description
The <b>KeLowerIrql</b> routine restores the IRQL on the current processor to its original value.



## -syntax

````
 VOID KeLowerIrql(
  _In_ KIRQL NewIrql
);
````


## -parameters

### -param NewIrql [in]

Specifies the IRQL that was returned from <a href="kernel.keraiseirql">KeRaiseIrql</a> or <a href="kernel.keraiseirqltodpclevel">KeRaiseIrqlToDpcLevel</a>.


## -returns
None


## -remarks
It is a fatal error to call <b>KeLowerIrql</b> using an input <i>NewIrql</i> that was not returned by the immediately preceding call to <b>KeRaiseIrql</b> or <a href="kernel.keraiseirqltodpclevel">KeRaiseIrqlToDpcLevel</a>.


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
Any level

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.wdm_irqlkeraiselower">IrqlKeRaiseLower</a>, <a href="devtest.wdm_irqlkeraiselower2">IrqlKeRaiseLower2</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.kegetcurrentirql">KeGetCurrentIrql</a>
</dt>
<dt>
<a href="kernel.keraiseirql">KeRaiseIrql</a>
</dt>
<dt>
<a href="kernel.keraiseirqltodpclevel">KeRaiseIrqlToDpcLevel</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeLowerIrql routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

