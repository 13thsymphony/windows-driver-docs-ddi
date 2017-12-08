---
UID: NF.wdm.InterlockedXor~r1
title: InterlockedXor function
author: windows-driver-content
description: The InterlockedOr routine atomically computes a bitwise exclusive OR operation.
old-location: kernel\interlockedxor.htm
old-project: kernel
ms.assetid: 3ddf62f1-ce5d-4d55-9964-8d1786ac2997
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: InterlockedXor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: InterlockedXor
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
req.product: Windows 10 or later.
---

# InterlockedXor function



## -description
The <b>InterlockedOr</b> routine atomically computes a bitwise exclusive OR operation.


## -syntax

````
LONG InterlockedXor(
  _Inout_ LONG volatile *Destination,
  _In_    LONG          Value
);
````


## -parameters

### -param Destination [in, out]

A pointer to the variable to be exclusive ORed with <i>Value</i>. The result of the operation is stored in the variable. 

### -param Value [in]

Specifies the value to be exclusive ORed with the variable that is pointed to by <i>Destination</i>. 

## -returns
<b>InterlockedXor</b> returns the original value stored in the variable pointed to by <i>Destination</i>.

## -remarks
<b>InterlockedXor</b> atomically computes <b>*</b><i>Destination</i><b>^=</b><i>Value</i>. 

Interlocked operations cannot be used on non-cached memory. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
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
IRQL
</th>
<td width="70%">
Any level
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.interlockedand">InterlockedAnd</a>
</dt>
<dt>
<a href="kernel.interlockedor">InterlockedOr</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20InterlockedXor routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
