---
UID: NC:drmk.PFNDRMCREATECONTENTMIXED
title: PFNDRMCREATECONTENTMIXED
author: windows-driver-content
description: This callback function is reserved for system use.
old-location: audio\pfndrmcreatecontentmixed.htm
old-project: audio
ms.assetid: A4BA818F-126F-4134-AEDA-F983ADFC4A07
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: DRMCreateContentMixed, DRMCreateContentMixed callback function [Audio Devices], PFNDRMCREATECONTENTMIXED, audio.pfndrmcreatecontentmixed, drmk/DRMCreateContentMixed
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Drmk.h
api_name:
-	DRMCreateContentMixed
product:
- Windows
targetos: Windows
req.typenames: WDI_TX_METADATA, *PWDI_TX_METADATA
---


# PFNDRMCREATECONTENTMIXED callback function
This callback function is reserved for system use.

## Syntax

```
PFNDRMCREATECONTENTMIXED Pfndrmcreatecontentmixed;

NTSTATUS Pfndrmcreatecontentmixed(
  PULONG paContentId,
  ULONG cContentId,
  PULONG pMixedContentId
)
{...}
```

## Parameters

`paContentId`

This parameter is reserved for system use.

`cContentId`

This parameter is reserved for system use.

`pMixedContentId`

This parameter is reserved for system use.


## Return Value

This return value is reserved for system use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | drmk.h |