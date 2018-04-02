---
UID: NF:sercx.SERCX_CONFIG_INIT
title: SERCX_CONFIG_INIT function
author: windows-driver-content
description: The SERCX_CONFIG_INIT function initializes a SERCX_CONFIG structure.
old-location: serports\sercx_config_init.htm
old-project: serports
ms.assetid: C7442A59-6D7C-4551-B0E4-F1E8A5BEB4B7
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 1/SERCX_CONFIG_INIT, SERCX_CONFIG_INIT, SERCX_CONFIG_INIT function [Serial Ports], serports.sercx_config_init
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
-	SERCX_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---


# SERCX_CONFIG_INIT function
The <b>SERCX_CONFIG_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439548">SERCX_CONFIG</a> structure.

## Syntax

```
void SERCX_CONFIG_INIT(
  SERCX_CONFIG *Config
);
```

## Parameters

`Config`

A pointer to the <b>SERCX_CONFIG</b> structure that is to be initialized.


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

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439548">SERCX_CONFIG</a>