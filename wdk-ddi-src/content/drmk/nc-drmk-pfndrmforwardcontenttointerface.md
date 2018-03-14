---
UID: NC:drmk.PFNDRMFORWARDCONTENTTOINTERFACE
title: PFNDRMFORWARDCONTENTTOINTERFACE
author: windows-driver-content
description: This callback function is reserved for system use.
old-location: audio\pfndrmforwardcontenttointerface.htm
old-project: audio
ms.assetid: DFD077B7-307B-439B-828D-DC225FC5AAA0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: DRMForwardContentToInterface, DRMForwardContentToInterface callback function [Audio Devices], PFNDRMFORWARDCONTENTTOINTERFACE, audio.pfndrmforwardcontenttointerface, drmk/DRMForwardContentToInterface
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
-	DRMForwardContentToInterface
product: Windows
targetos: Windows
req.typenames: WDI_TX_METADATA, *PWDI_TX_METADATA
---


# PFNDRMFORWARDCONTENTTOINTERFACE callback function
This callback function is reserved for system use.

## Syntax

```
PFNDRMFORWARDCONTENTTOINTERFACE Pfndrmforwardcontenttointerface;

NTSTATUS Pfndrmforwardcontenttointerface(
  ULONG ContentId,
  PUNKNOWN pUnknown,
  ULONG NumMethods
)
{...}
```

## Parameters

`ContentId`

This parameter is reserved for system use.

`pUnknown`

This parameter is reserved for system use.

`NumMethods`

This parameter is reserved for system use.


## Return Value

This return value is reserved for system use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | drmk.h |