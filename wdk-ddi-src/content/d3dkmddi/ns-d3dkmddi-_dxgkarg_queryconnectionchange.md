---
UID: NS:d3dkmddi._DXGKARG_QUERYCONNECTIONCHANGE
title: "_DXGKARG_QUERYCONNECTIONCHANGE"
author: windows-driver-content
description: Used to hold the arguments for DXGKDDI_QUERYCONNECTIONCHANGE.
old-location: display\dxgkarg_queryconnectionchange.htm
old-project: display
ms.assetid: 6B91F3F0-B02D-46F3-9086-EA32F043FC16
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGKARG_QUERYCONNECTIONCHANGE, DXGKARG_QUERYCONNECTIONCHANGE, _DXGKARG_QUERYCONNECTIONCHANGE, *IN_PDXGKARG_QUERYCONNECTIONCHANGE, DXGKARG_QUERYCONNECTIONCHANGE structure [Display Devices], display.dxgkarg_queryconnectionchange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARG_QUERYCONNECTIONCHANGE
product: Windows
targetos: Windows
req.typenames: DXGKARG_QUERYCONNECTIONCHANGE
---

# _DXGKARG_QUERYCONNECTIONCHANGE structure
Used to hold the arguments for <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryconnectionchange.md">DXGKDDI_QUERYCONNECTIONCHANGE</a>.

## Syntax
````
typedef struct _DXGKARG_QUERYCONNECTIONCHANGE {
  DXGK_CONNECTION_CHANGE ConnectionChange;
} DXGKARG_QUERYCONNECTIONCHANGE;
````

## Members


`ConnectionChange`

[out] Buffer into which the oldest available change is copied by driver.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmddi.h |