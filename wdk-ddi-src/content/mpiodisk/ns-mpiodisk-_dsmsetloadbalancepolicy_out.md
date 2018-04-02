---
UID: NS:mpiodisk._DsmSetLoadBalancePolicy_OUT
title: "_DsmSetLoadBalancePolicy_OUT"
author: windows-driver-content
description: The DsmSetLoadBalancePolicy_OUT structure reports the output parameter of the DsmSetLoadBalancePolicy method.
old-location: storage\dsmsetloadbalancepolicy_out.htm
old-project: storage
ms.assetid: d3479656-310f-4e2d-a671-296bc3e2f1ab
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDsmSetLoadBalancePolicy_OUT, DsmSetLoadBalancePolicy_OUT, DsmSetLoadBalancePolicy_OUT structure [Storage Devices], PDsmSetLoadBalancePolicy_OUT, PDsmSetLoadBalancePolicy_OUT structure pointer [Storage Devices], _DsmSetLoadBalancePolicy_OUT, mpiodisk/DsmSetLoadBalancePolicy_OUT, mpiodisk/PDsmSetLoadBalancePolicy_OUT, storage.dsmsetloadbalancepolicy_out, structs-scsibus_f22d33bc-ce52-4369-8dd2-085c393a9107.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	mpiodisk.h
api_name:
-	DsmSetLoadBalancePolicy_OUT
product:
- Windows
targetos: Windows
req.typenames: DsmSetLoadBalancePolicy_OUT, *PDsmSetLoadBalancePolicy_OUT
---

# _DsmSetLoadBalancePolicy_OUT structure
The <b>DsmSetLoadBalancePolicy_OUT</b> structure reports the output parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552670">DsmSetLoadBalancePolicy</a> method.

## Syntax
```
typedef struct _DsmSetLoadBalancePolicy_OUT {
  ULONG Status;
} *PDsmSetLoadBalancePolicy_OUT, DsmSetLoadBalancePolicy_OUT;
```

## Members


`Status`

The status of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552670">DsmSetLoadBalancePolicy</a> operation.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | mpiodisk.h (include Mpiowmi.h) |