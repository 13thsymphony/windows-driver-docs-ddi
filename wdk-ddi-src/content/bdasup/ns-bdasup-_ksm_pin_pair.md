---
UID: NS:bdasup._KSM_PIN_PAIR
title: "_KSM_PIN_PAIR"
author: windows-driver-content
description: The KSM_PIN_PAIR structure describes a method request to retrieve the pin pairing structure (BDA_PIN_PAIRING) between a pair of input and output pins.
old-location: stream\ksm_pin_pair.htm
old-project: stream
ms.assetid: a38e1215-4689-4b75-9a32-4d6570694b77
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PKSM_PIN_PAIR, bdasup/PKSM_PIN_PAIR, bdasup/KSM_PIN_PAIR, stream.ksm_pin_pair, _KSM_PIN_PAIR, *PKSM_PIN_PAIR, bdaref_4d2071d5-ba64-4026-95a9-0763dc2f13cf.xml, PKSM_PIN_PAIR structure pointer [Streaming Media Devices], KSM_PIN_PAIR structure [Streaming Media Devices], KSM_PIN_PAIR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdasup.h
req.include-header: Bdasup.h
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
-	bdasup.h
apiname:
-	KSM_PIN_PAIR
product: Windows
targetos: Windows
req.typenames: "*PKSM_PIN_PAIR, KSM_PIN_PAIR"
---

# _KSM_PIN_PAIR structure
The KSM_PIN_PAIR structure describes a method request to retrieve the pin pairing structure (BDA_PIN_PAIRING) between a pair of input and output pins.

## Syntax
````
typedef struct _KSM_PIN_PAIR {
  KSMETHOD Method;
  ULONG    InputPinId;
  ULONG    OutputPinId;
  ULONG    Reserved;
} KSM_PIN_PAIR, *PKSM_PIN_PAIR;
````

## Members


`InputPinId`

Identifier of an input pin of the filter.

`Method`

KSMETHOD structure that describes a method and request type of a method request.

`OutputPinId`

Identifier of an output pin of the filter.

`Reserved`

Reserved.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | bdasup.h (include Bdasup.h) |

## See Also

<a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a>

<a href="..\bdasup\ns-bdasup-_bda_pin_pairing.md">BDA_PIN_PAIRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSM_PIN_PAIR structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>