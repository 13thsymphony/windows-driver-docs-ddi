---
UID: NF.ndis.NdisInterlockedAddLargeStatistic
title: NdisInterlockedAddLargeStatistic macro
author: windows-driver-content
description: The NdisInterlockedAddLargeStatistic function performs an interlocked addition of a ULONG increment value to a LARGE_INTEGER addend value.
old-location: netvista\ndisinterlockedaddlargestatistic.htm
old-project: NetVista
ms.assetid: 7bc753b1-5e09-431b-b226-fb7194dd6947
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisInterlockedAddLargeStatistic
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisInterlockedAddLargeStatistic (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisInterlockedAddLargeStatistic (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisInterlockedAddLargeStatistic
req.alt-loc: ndis.h
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
---

# NdisInterlockedAddLargeStatistic macro



## -description
The 
  <b>NdisInterlockedAddLargeStatistic</b> function performs an interlocked addition of a ULONG increment value
  to a LARGE_INTEGER addend value.



## -syntax

````
VOID NdisInterlockedAddLargeStatistic(
  [in] PLARGE_INTEGER Addend,
  [in] ULONG          Increment
);
````


## -parameters

### -param Addend [in]

A pointer to a LARGE_INTEGER value that is incremented by the value of 
     <i>Increment</i> .


### -param Increment [in]

A ULONG value that is added to the value to which the 
     <i>Addend</i> parameter points.


## -remarks
Functions that perform interlocked operations must not cause a page fault to occur. Neither their code
    nor any of the data that they access can cause a page fault without bringing down the local computer.

<b>NdisInterlockedAddLargeStatistic</b> masks interrupts and can be safely used to synchronize a driver's 
    <a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a> function with other
    driver code.


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
Version

</th>
<td width="70%">
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/320f0f61-3b59-4187-a956-35df94961fe4">
   NdisInterlockedAddLargeStatistic (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>
   NdisInterlockedAddLargeStatistic (NDIS 5.1)</b>) in Windows XP.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
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
<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisInterlockedAddLargeStatistic macro%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

