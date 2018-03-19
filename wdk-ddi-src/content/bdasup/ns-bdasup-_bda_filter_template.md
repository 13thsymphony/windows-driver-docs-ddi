---
UID: NS:bdasup._BDA_FILTER_TEMPLATE
title: "_BDA_FILTER_TEMPLATE"
author: windows-driver-content
description: The BDA_FILTER_TEMPLATE structure describes the template topology for a BDA filter.
old-location: stream\bda_filter_template.htm
old-project: stream
ms.assetid: 93078225-3487-46db-b13e-e2013be86d97
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PBDA_FILTER_TEMPLATE, BDA_FILTER_TEMPLATE, BDA_FILTER_TEMPLATE structure [Streaming Media Devices], PBDA_FILTER_TEMPLATE, PBDA_FILTER_TEMPLATE structure pointer [Streaming Media Devices], _BDA_FILTER_TEMPLATE, bdaref_cf65795d-632d-4c79-9136-95c256ae8b35.xml, bdasup/BDA_FILTER_TEMPLATE, bdasup/PBDA_FILTER_TEMPLATE, stream.bda_filter_template"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bdasup.h
api_name:
-	BDA_FILTER_TEMPLATE
product: Windows
targetos: Windows
req.typenames: BDA_FILTER_TEMPLATE, *PBDA_FILTER_TEMPLATE
---

# _BDA_FILTER_TEMPLATE structure
The BDA_FILTER_TEMPLATE structure describes the template topology for a BDA filter.

## Syntax
````
typedef struct _BDA_FILTER_TEMPLATE {
  const KSFILTER_DESCRIPTOR *pFilterDescriptor;
  ULONG                     ulcPinPairs;
  const BDA_PIN_PAIRING     *pPinPairs;
} BDA_FILTER_TEMPLATE, *PBDA_FILTER_TEMPLATE;
````

## Members


`pFilterDescriptor`

Points to a KSFILTER_DESCRIPTOR structure that describes a template for a filter for the BDA device.

`ulcPinPairs`

Number of pairs of pins in the <b>pPinPairs</b> array.

`pPinPairs`

Array of BDA_PIN_PAIRING structures that describe the topology between a pair of the filter's input and output pins.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | bdasup.h (include Bdasup.h) |

## See Also

<a href="..\bdasup\nf-bdasup-bdainitfilter.md">BdaInitFilter</a>



<a href="..\bdasup\ns-bdasup-_bda_pin_pairing.md">BDA_PIN_PAIRING</a>



<a href="..\bdasup\nf-bdasup-bdacreatefilterfactory.md">BdaCreateFilterFactory</a>



<a href="..\ks\ns-ks-_ksfilter_descriptor.md">KSFILTER_DESCRIPTOR</a>