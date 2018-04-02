---
UID: NS:bdamedia._KSM_BDA_PIN_PAIR
title: "_KSM_BDA_PIN_PAIR"
author: windows-driver-content
description: The KSM_BDA_PIN_PAIR structure describes a method request to retrieve the pin pairing structure (BDA_PIN_PAIRING) between a pair of input and output pins.
old-location: stream\ksm_bda_pin_pair.htm
old-project: stream
ms.assetid: 310a3faf-de71-4965-9511-cb8feca7087c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSM_BDA_PIN_PAIR, KSM_BDA_PIN_PAIR, KSM_BDA_PIN_PAIR structure [Streaming Media Devices], PKSM_BDA_PIN_PAIR, PKSM_BDA_PIN_PAIR structure pointer [Streaming Media Devices], _KSM_BDA_PIN_PAIR, bdamedia/KSM_BDA_PIN_PAIR, bdamedia/PKSM_BDA_PIN_PAIR, bdaref_c171cffc-e7e6-432b-98ae-f198fdc20079.xml, stream.ksm_bda_pin_pair"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdamedia.h
req.include-header: Bdamedia.h
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
-	HeaderDef
api_location:
-	bdamedia.h
api_name:
-	KSM_BDA_PIN_PAIR
product: Windows
targetos: Windows
req.typenames: KSM_BDA_PIN_PAIR, *PKSM_BDA_PIN_PAIR
---

# _KSM_BDA_PIN_PAIR structure
The KSM_BDA_PIN_PAIR structure describes a method request to retrieve the pin pairing structure (BDA_PIN_PAIRING) between a pair of input and output pins.

## Syntax
```
typedef struct _KSM_BDA_PIN_PAIR {
  KSMETHOD Method;
  union {
    ULONG InputPinId;
    ULONG InputPinType;
  };
  union {
    ULONG OutputPinId;
    ULONG OutputPinType;
  };
} KSM_BDA_PIN_PAIR, *PKSM_BDA_PIN_PAIR;
```

## Members


`Method`

KSMETHOD structure that describes a method and request type of a method request.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | bdamedia.h (include Bdamedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556544">BDA_PIN_PAIRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563398">KSMETHOD</a>