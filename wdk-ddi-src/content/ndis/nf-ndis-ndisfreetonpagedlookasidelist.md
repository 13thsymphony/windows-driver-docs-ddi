---
UID: NF.ndis.NdisFreeToNPagedLookasideList
title: NdisFreeToNPagedLookasideList macro
author: windows-driver-content
description: The NdisFreeToNPagedLookasideList function returns an entry to the given lookaside list.
old-location: netvista\ndisfreetonpagedlookasidelist.htm
old-project: NetVista
ms.assetid: 2405a405-177a-420a-9628-a340e0d0acb3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisFreeToNPagedLookasideList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisFreeToNPagedLookasideList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisFreeToNPagedLookasideList (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisFreeToNPagedLookasideList
req.alt-loc: ndis.h
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# NdisFreeToNPagedLookasideList macro



## -description
The 
  <b>NdisFreeToNPagedLookasideList</b> function returns an entry to the given lookaside list.



## -syntax

````
VOID NdisFreeToNPagedLookasideList(
  [in] PNPAGED_LOOKASIDE_LIST Lookaside,
  [in] PVOID                  Entry
);
````


## -parameters

### -param Lookaside [in]

A pointer to the head of the lookaside list to which the entry will be returned.


### -param Entry [in]

A pointer to the entry to be freed.


## -remarks
If the lookaside list has not reached the system-determined maximum number of entries, 
    <i>Entry</i> is inserted at the front of the lookaside list. If the list has reached its maximum size, 
    <i>Entry</i> is released to nonpaged pool. That is, 
    <b>NdisFreeToNPagedLookasideList</b> either calls the driver's 
    <i>Free</i> function, specified in the 
    <i>Free</i> parameter if the driver provided one to the 
    <a href="netvista.ndisinitializenpagedlookasidelist">
    NdisInitializeNPagedLookasideList</a> function, or it frees the given entry itself.


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
   <a href="https://msdn.microsoft.com/2ae736bc-f91c-4c93-9532-f0d366283335">
   NdisFreeToNPagedLookasideList (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>
   NdisFreeToNPagedLookasideList (NDIS 5.1)</b>) in Windows XP.

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
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_irql_miscellaneous_function">Irql_Miscellaneous_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndisallocatefromnpagedlookasidelist">
   NdisAllocateFromNPagedLookasideList</a>
</dt>
<dt>
<a href="netvista.ndisdeletenpagedlookasidelist">
   NdisDeleteNPagedLookasideList</a>
</dt>
<dt>
<a href="netvista.ndisinitializenpagedlookasidelist">
   NdisInitializeNPagedLookasideList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisFreeToNPagedLookasideList macro%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

