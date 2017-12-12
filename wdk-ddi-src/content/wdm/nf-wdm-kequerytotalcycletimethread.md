---
UID: NF.wdm.KeQueryTotalCycleTimeThread
title: KeQueryTotalCycleTimeThread function
author: windows-driver-content
description: The KeQueryTotalCycleTimeThread routine returns the accumulated cycle time for the specified thread.
old-location: kernel\kequerytotalcycletimethread_.htm
old-project: kernel
ms.assetid: EC3A5F02-3D04-466E-8EB4-4BDA9CE47886
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: KeQueryTotalCycleTimeThread
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeQueryTotalCycleTimeThread
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# KeQueryTotalCycleTimeThread function



## -description
The <b>KeQueryTotalCycleTimeThread</b> routine returns the accumulated cycle time for the specified thread.



## -syntax

````
ULONG64 KeQueryTotalCycleTimeThread (
  _Inout_ PKTHREAD Thread,
  _Out_   PULONG64 CycleTimeStamp
);
````


## -parameters

### -param Thread [in, out]

A pointer to a dispatcher object of type KTHREAD.


### -param CycleTimeStamp [out]

A pointer to the cycle counter value at the time of the query.


## -returns
The accumulated cycle time for the thread.


## -remarks


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
Available in Windows 8 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h</dt>
</dl>
</td>
</tr>
</table>