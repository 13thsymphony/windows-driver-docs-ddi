---
UID: NS:bdatypes._BDA_DISEQC_SEND
title: "_BDA_DISEQC_SEND"
author: windows-driver-content
description: "."
old-location: stream\bda_diseqc_send.htm
old-project: stream
ms.assetid: C40EAB5C-61AA-45FB-856E-07AB4D0228A6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: BDA_DISEQC_SEND, bdatypes/BDA_DISEQC_SEND, PBDA_DISEQC_SEND, PBDA_DISEQC_SEND structure pointer [Streaming Media Devices], bdatypes/PBDA_DISEQC_SEND, *PBDA_DISEQC_SEND, _BDA_DISEQC_SEND, stream.bda_diseqc_send, BDA_DISEQC_SEND structure [Streaming Media Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Bdatypes.h
apiname:
-	BDA_DISEQC_SEND
product: Windows
targetos: Windows
req.typenames: "*PBDA_DISEQC_SEND, BDA_DISEQC_SEND"
---

# _BDA_DISEQC_SEND structure


## Syntax
````
typedef struct _BDA_DISEQC_SEND {
  ULONG ulRequestId;
  ULONG ulPacketLength;
  BYTE  argbPacketData[8];
} BDA_DISEQC_SEND, *PBDA_DISEQC_SEND;
````

## Members


`argbPacketData`



`ulPacketLength`



`ulRequestId`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | bdatypes.h |