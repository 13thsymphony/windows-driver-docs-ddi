---
UID: NC:drmk.PFNDRMGETCONTENTRIGHTS
title: PFNDRMGETCONTENTRIGHTS
author: windows-driver-content
description: This callback function is reserved for system use.
old-location: audio\pfndrmgetcontentrights.htm
old-project: audio
ms.assetid: 1230C71C-9C1A-4F1F-8AA7-C814249675B5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.pfndrmgetcontentrights, DRMGetContentRights callback function [Audio Devices], DRMGetContentRights, PFNDRMGETCONTENTRIGHTS, PFNDRMGETCONTENTRIGHTS, drmk/DRMGetContentRights, DRMGetContentRights callback function [Audio Devices], DRMGetContentRights
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
-	DRMGetContentRights
product: Windows
targetos: Windows
req.typenames: WDI_TX_METADATA, *PWDI_TX_METADATA
---


# PFNDRMGETCONTENTRIGHTS callback function
This callback function is reserved for system use.

## Syntax

```
PFNDRMGETCONTENTRIGHTS Pfndrmgetcontentrights;

NTSTATUS Pfndrmgetcontentrights(
  ULONG ContentId,
  PDRMRIGHTS DrmRights
)
{...}
```

## Parameters

`ContentId`

This parameter is reserved for system use.

`DrmRights`

This parameter is reserved for system use.


## Return Value

This return value is reserved for system use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | drmk.h |