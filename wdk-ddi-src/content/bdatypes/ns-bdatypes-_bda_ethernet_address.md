---
UID: NS:bdatypes._BDA_ETHERNET_ADDRESS
title: "_BDA_ETHERNET_ADDRESS"
author: windows-driver-content
description: "."
old-location: stream\bda_ethernet_address.htm
old-project: stream
ms.assetid: F4B9A413-7FB5-4CA3-9731-A143CB0D7346
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PBDA_ETHERNET_ADDRESS, BDA_ETHERNET_ADDRESS, BDA_ETHERNET_ADDRESS structure [Streaming Media Devices], PBDA_ETHERNET_ADDRESS, PBDA_ETHERNET_ADDRESS structure pointer [Streaming Media Devices], _BDA_ETHERNET_ADDRESS, bdatypes/BDA_ETHERNET_ADDRESS, bdatypes/PBDA_ETHERNET_ADDRESS, stream.bda_ethernet_address"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Bdatypes.h
api_name:
-	BDA_ETHERNET_ADDRESS
product: Windows
targetos: Windows
req.typenames: BDA_ETHERNET_ADDRESS, *PBDA_ETHERNET_ADDRESS
---

# _BDA_ETHERNET_ADDRESS structure


## Syntax
````
typedef struct _BDA_ETHERNET_ADDRESS {
  BYTE rgbAddress[6];
} BDA_ETHERNET_ADDRESS, *PBDA_ETHERNET_ADDRESS;
````

## Members


`rgbAddress`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | bdatypes.h |