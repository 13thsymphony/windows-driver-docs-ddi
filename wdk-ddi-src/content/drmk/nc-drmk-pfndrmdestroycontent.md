---
UID: NC:drmk.PFNDRMDESTROYCONTENT
title: PFNDRMDESTROYCONTENT
author: windows-driver-content
description: This callback function is reserved for system use.
old-location: audio\pfndrmdestroycontent.htm
old-project: audio
ms.assetid: 24B98C91-9EB3-4D00-8D58-F6C96610946A
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: audio.pfndrmdestroycontent, DRMDestroyContent callback function [Audio Devices], DRMDestroyContent, PFNDRMDESTROYCONTENT, PFNDRMDESTROYCONTENT, drmk/DRMDestroyContent, DRMDestroyContent callback function [Audio Devices], DRMDestroyContent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: drmk.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Drmk.h
apiname:
-	DRMDestroyContent
product: Windows
targetos: Windows
req.typenames: "*PWDI_TX_METADATA, WDI_TX_METADATA"
---


# PFNDRMDESTROYCONTENT callback function
This callback function is reserved for system use.

## Syntax

```
PFNDRMDESTROYCONTENT Pfndrmdestroycontent;

NTSTATUS Pfndrmdestroycontent(
  ULONG ContentId
)
{...}
```

## Parameters

`ContentId`

This parameter is reserved for system use.


## Return Value

This return value is reserved for system use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | drmk.h |