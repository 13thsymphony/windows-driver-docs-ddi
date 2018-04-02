---
UID: NC:bthsdpddi.PRETRIEVEUINT64
title: PRETRIEVEUINT64
author: windows-driver-content
description: The Bluetooth SdpRetrieveUint128 function is used to copy an unaligned 128-bit integer from an SDP stream.
old-location: bltooth\sdpretrieveuint128.htm
old-project: bltooth
ms.assetid: fa187750-1aed-4e74-8e98-a3b8c731f1d1
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PRETRIEVEUINT64, SdpRetrieveUint128, SdpRetrieveUint128 callback function [Bluetooth Devices], bltooth.sdpretrieveuint128, bth_funcs_5377ee2b-643e-4486-9eb2-6d37bda46c85.xml, sdplib/SdpRetrieveUint128
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: bthsdpddi.h
req.include-header: BthSdpddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	sdplib.h
api_name:
-	SdpRetrieveUint128
product:
- Windows
targetos: Windows
req.typenames: BTH_VENDOR_SPECIFIC_COMMAND, *PBTH_VENDOR_SPECIFIC_COMMAND
---


# PRETRIEVEUINT64 callback function
The Bluetooth 
  <b>SdpRetrieveUint128</b> function is used to copy an unaligned 128-bit integer from an SDP stream.

## Syntax

```
PRETRIEVEUINT64 Pretrieveuint64;

void Pretrieveuint64(
  PUCHAR Stream,
  PULONGLONG pUint16
)
{...}
```

## Parameters

`Stream`

A pointer to an unaligned 128-bit integer.

`pUint16`




## Return Value

None

## Remarks

The 
    <b>SdpRetrieveUint128</b> function does not search for the unaligned integer to copy. The 
    <i>Stream</i> parameter must specify the exact address of the unsigned integer to be extracted.

Some processor architectures require that values be aligned in memory and will generate an error if an
    attempt is made to access a misaligned value. SDP records are constructed without regard to processor
    alignment rules. When SDP records are stored in memory, they might contain elements that are misaligned
    according to local processor's alignment rules.

The 
    <b>SdpRetrieveUint128</b> function safely copies unaligned integers on computers that have alignment
    requirements and efficiently copies unaligned integers on computers that do not have requirements. In
    addition, this function works on integers that are aligned correctly.

This function has no effect on byte order.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="https://msdn.microsoft.com/bb8a1dd5-8207-4034-993e-eed49dc0f9c4">
    BTHDDI_SDP_PARSE_INTERFACE</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later.  |
| **Target Platform** | Desktop |
| **Header** | bthsdpddi.h (include BthSdpddi.h) |
| **IRQL** | "<= PASSIVE_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536636">BTHDDI_SDP_PARSE_INTERFACE</a>