---
UID: NS.MPIODISK._DSMSETLOADBALANCEPOLICYALUA_IN
title: _DsmSetLoadBalancePolicyALUA_IN
author: windows-driver-content
description: The DsmSetLoadBalancePolicyALUA_IN structure provides the input parameter for the DsmSetLoadBalancePolicyALUA method.
old-location: storage\dsmsetloadbalancepolicyalua_in.htm
old-project: storage
ms.assetid: d46cfba0-a749-436a-99ad-d3606aea9a4d
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _DsmSetLoadBalancePolicyALUA_IN, *PDsmSetLoadBalancePolicyALUA_IN, DsmSetLoadBalancePolicyALUA_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mpiodisk.h
req.include-header: Mpiowmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DsmSetLoadBalancePolicyALUA_IN
req.alt-loc: mpiodisk.h
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
---

# _DsmSetLoadBalancePolicyALUA_IN structure



## -description
The DsmSetLoadBalancePolicyALUA_IN structure provides the input parameter for the DsmSetLoadBalancePolicyALUA method.


## -syntax

````
typedef struct _DsmSetLoadBalancePolicyALUA_IN {
  DSM_Load_Balance_Policy_V2 LoadBalancePolicy;
} DsmSetLoadBalancePolicyALUA_IN, *PDsmSetLoadBalancePolicyALUA_IN;
````


## -struct-fields

### -field LoadBalancePolicy

A structure of type DSM_Load_Balance_Policy_V2.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Mpiodisk.h (include Mpiowmi.h)</dt>
</dl>
</td>
</tr>
</table>