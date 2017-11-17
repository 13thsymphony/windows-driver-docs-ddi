---
UID: NF.wdm.InterlockedAnd~r1
title: InterlockedAnd
author: windows-driver-content
description: The InterlockedAnd macro atomically computes a bitwise AND operation.
old-location: kernel\interlockedand.htm
ms.assetid: 3b1ff981-7f87-4a47-81a3-3e323459c333
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: InterlockedAnd
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
ms.keywords: InterlockedAnd
req.iface: 
req.product: Windows 10 or later.
---

# InterlockedAnd function



## -description
<p>The <b>InterlockedAnd</b> macro atomically computes a bitwise AND operation.</p>


## -syntax

````
LONG InterlockedAnd(
  _Inout_ LONG volatile *Destination,
  _In_    LONG          Value
);
````


## -parameters
<dl>

### -param <i>Destination</i> [in, out]

<dd>
<p>A pointer to the variable to be ANDed with <i>Value</i>. The result of the operation is stored in the variable.</p>
</dd>

### -param <i>Value</i> [in]

<dd>
<p>Specifies the value to be ANDed with the variable that is pointed to by <i>Destination</i>. </p>
</dd>
</dl>

## -returns
<p><b>InterlockedAnd</b> returns the original value stored in the variable pointed to by <i>Destination</i>. </p>

## -remarks
<p><b>InterlockedAnd</b> atomically computes <b>*</b><i>Destination</i><b>&amp;=</b><i>Value</i>.</p>

<p>Interlocked operations cannot be used on non-cached memory. </p>

<p><b>InterlockedAnd</b> atomically computes <b>*</b><i>Destination</i><b>&amp;=</b><i>Value</i>.</p>

<p>Interlocked operations cannot be used on non-cached memory. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 2000.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547928">InterlockedOr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547933">InterlockedXor</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20InterlockedAnd function%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
