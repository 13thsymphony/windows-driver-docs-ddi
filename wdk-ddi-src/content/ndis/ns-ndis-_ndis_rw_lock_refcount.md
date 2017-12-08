---
UID: NS.NDIS._NDIS_RW_LOCK_REFCOUNT
title: _NDIS_RW_LOCK_REFCOUNT
author: windows-driver-content
description: The NDIS_RW_LOCK_REFCOUNT union defines attributes of a read/write lock.
old-location: netvista\ndis_rw_lock_refcount.htm
old-project: netvista
ms.assetid: 1b2c93dd-a80e-4197-bc4f-cad12f6d6c77
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _NDIS_RW_LOCK_REFCOUNT, NDIS_RW_LOCK_REFCOUNT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Obsolete in NDIS 6.20 and later. Supported for NDIS 6.0 and NDIS 5.1 in   Windows Vista and Windows 7. Supported for NDIS 5.1 drivers in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_RW_LOCK_REFCOUNT
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

# _NDIS_RW_LOCK_REFCOUNT structure



## -description
The <b>NDIS_RW_LOCK_REFCOUNT</b> union defines attributes of a read/write lock. This union is opaque to NDIS
   drivers.
   


## -syntax

````
typedef union _NDIS_RW_LOCK_REFCOUNT {
  ;      // Reserved for NDIS.
} NDIS_RW_LOCK_REFCOUNT;
````


## -struct-fields


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Obsolete in NDIS 6.20 and later. Supported for NDIS 6.0 and NDIS 5.1 in
   Windows Vista and Windows 7. Supported for NDIS 5.1 drivers in Windows XP.
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
</table>