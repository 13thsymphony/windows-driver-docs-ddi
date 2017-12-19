---
UID: NF.storport.StorPortGetNodeAffinity
title: StorPortGetNodeAffinity function
author: windows-driver-content
description: The StorPortGetNodeAffinity routine constructs a mask of the active processors in a requested non-uniform memory access (NUMA) node.
old-location: storage\storportgetnodeaffinity.htm
old-project: storage
ms.assetid: 183940c9-f8d9-411f-a593-e283f72e05f8
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: StorPortGetNodeAffinity
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortGetNodeAffinity
req.alt-loc: storport.h
req.ddi-compliance: StorPortIrql
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# StorPortGetNodeAffinity function



## -description
The <b>StorPortGetNodeAffinity</b> routine constructs a mask of the active processors in a requested non-uniform memory access (NUMA) node.



## -syntax

````
ULONG StorPortGetNodeAffinity(
  _In_  PVOID           HwDeviceExtension,
  _In_  ULONG           NodeNumber,
  _Out_ PGROUP_AFFINITY NodeAffinityMask
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param NodeNumber [in]

The NUMA node from which to return the processor mask.


### -param NodeAffinityMask [out]

A pointer to a variable that holds the affinity mask of the given node.


## -returns
The <b>StorPortGetNodeAffinity</b>routine returns one of the following status codes:
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>This function is not implemented on the active operating system.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>The operation was successful.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>The operation fails with this return value if one or more of the parameters are invalid, for example, if <i>NodeAffinityMask</i> is set to <b>NULL</b>, or if <i>NodeNumber</i> is greater than 65,535.

 


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
Available in Windows 7 and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.storport_storportirql">StorPortIrql</a>
</td>
</tr>
</table>