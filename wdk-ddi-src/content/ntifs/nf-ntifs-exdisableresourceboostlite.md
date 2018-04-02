---
UID: NF:ntifs.ExDisableResourceBoostLite
title: ExDisableResourceBoostLite function
author: windows-driver-content
description: Reserved for system use.
old-location: ifsk\exdisableresourceboostlite.htm
old-project: ifsk
ms.assetid: 0ab2d417-56d8-4047-846d-6ae4cbaa8409
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ExDisableResourceBoostLite, ExDisableResourceBoostLite function [Installable File System Drivers], exref_7c451751-995b-4d3c-9445-25b337624ef7.xml, ifsk.exdisableresourceboostlite, ntifs/ExDisableResourceBoostLite
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
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
-	ntifs.h
api_name:
-	ExDisableResourceBoostLite
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# ExDisableResourceBoostLite function
This routine is reserved for system use. Do not use this routine in your driver.

## Syntax

```
NTKERNELAPI VOID ExDisableResourceBoostLite(
  PERESOURCE Resource
);
```

## Parameters

`Resource`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ntifs.h (include Ntifs.h) |