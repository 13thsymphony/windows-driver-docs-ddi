---
UID : NS:bdatypes._BDA_IPv6_ADDRESS_LIST
title : "_BDA_IPv6_ADDRESS_LIST"
author : windows-driver-content
description : "."
old-location : stream\bda_ipv6_address_list.htm
old-project : stream
ms.assetid : 45C8C690-7545-47D5-8E98-FB976797AA1A
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : BDA_IPv6_ADDRESS_LIST structure [Streaming Media Devices], stream.bda_ipv6_address_list, PBDA_IPv6_ADDRESS_LIST structure pointer [Streaming Media Devices], *PBDA_IPv6_ADDRESS_LIST, bdatypes/PBDA_IPv6_ADDRESS_LIST, bdatypes/BDA_IPv6_ADDRESS_LIST, _BDA_IPv6_ADDRESS_LIST, PBDA_IPv6_ADDRESS_LIST, BDA_IPv6_ADDRESS_LIST
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
req.typenames : "*PBDA_IPv6_ADDRESS_LIST, BDA_IPv6_ADDRESS_LIST"
---

# _BDA_IPv6_ADDRESS_LIST structure


## Syntax
````
typedef struct _BDA_IPv6_ADDRESS_LIST {
  ULONG            ulcAddresses;
  BDA_IPv6_ADDRESS rgAddressl[MIN_DIMENSION];
} BDA_IPv6_ADDRESS_LIST, *PBDA_IPv6_ADDRESS_LIST;
````

## Members


`rgAddressl`



`ulcAddresses`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | bdatypes.h |