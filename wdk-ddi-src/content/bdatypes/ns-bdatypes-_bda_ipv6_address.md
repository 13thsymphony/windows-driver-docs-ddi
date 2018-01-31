---
UID : NS:bdatypes._BDA_IPv6_ADDRESS
title : "_BDA_IPv6_ADDRESS"
author : windows-driver-content
description : "."
old-location : stream\bda_ipv6_address.htm
old-project : stream
ms.assetid : 50D52380-1FBE-4046-A7DC-8415501D7FA6
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : bdatypes/BDA_IPv6_ADDRESS, PBDA_IPv6_ADDRESS structure pointer [Streaming Media Devices], BDA_IPv6_ADDRESS structure [Streaming Media Devices], *PBDA_IPv6_ADDRESS, PBDA_IPv6_ADDRESS, stream.bda_ipv6_address, BDA_IPv6_ADDRESS, _BDA_IPv6_ADDRESS, bdatypes/PBDA_IPv6_ADDRESS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : bdatypes.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PBDA_IPv6_ADDRESS, BDA_IPv6_ADDRESS"
---

# _BDA_IPv6_ADDRESS structure


## Syntax
````
typedef struct _BDA_IPv6_ADDRESS {
  BYTE rgbAddress[6];
} BDA_IPv6_ADDRESS, *PBDA_IPv6_ADDRESS;
````

## Members


`rgbAddress`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bdatypes.h |