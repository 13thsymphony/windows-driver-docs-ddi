---
UID: NF:sercx.SERCX_ACTIVITY_INIT
title: SERCX_ACTIVITY_INIT function
author: windows-driver-content
description: The SERCX_ACTIVITY_INIT function initializes a SERCX_ACTIVITY structure.
old-location: serports\sercx_activity_init.htm
old-project: serports
ms.assetid: 211A3DBB-96B8-4DB5-BB50-FAB7500D999F
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 1/SERCX_ACTIVITY_INIT, SERCX_ACTIVITY_INIT, SERCX_ACTIVITY_INIT function [Serial Ports], serports.sercx_activity_init
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: Any IRQL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	1.0\Sercx.h
api_name:
-	SERCX_ACTIVITY_INIT
product:
- Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---


# SERCX_ACTIVITY_INIT function
The <b>SERCX_ACTIVITY_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439527">SERCX_ACTIVITY</a> structure.

## Syntax

```
void SERCX_ACTIVITY_INIT(
  SERCX_ACTIVITY *Activity
);
```

## Parameters

`Activity`

A pointer to the <b>SERCX_ACTIVITY</b> structure that is to be initialized.


## Return Value

None.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.  |
| **Target Platform** | Desktop |
| **Header** | sercx.h |
| **IRQL** | Any IRQL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439527">SERCX_ACTIVITY</a>