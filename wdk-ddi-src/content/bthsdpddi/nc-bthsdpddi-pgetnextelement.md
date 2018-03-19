---
UID: NC:bthsdpddi.PGETNEXTELEMENT
title: PGETNEXTELEMENT
author: windows-driver-content
description: The Bluetooth SdpGetNextElement function is used to iterate through the entries found in an SDP record stream.
old-location: bltooth\sdpgetnextelement.htm
old-project: bltooth
ms.assetid: 60216196-f8c7-4555-a461-4862ce6bc376
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PGETNEXTELEMENT, SdpGetNextElement, SdpGetNextElement callback function [Bluetooth Devices], bltooth.sdpgetnextelement, bth_funcs_344a59cb-6151-4634-bc5f-cb23c58eb329.xml, sdplib/SdpGetNextElement
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
-	SdpGetNextElement
product: Windows
targetos: Windows
req.typenames: BTH_VENDOR_SPECIFIC_COMMAND, *PBTH_VENDOR_SPECIFIC_COMMAND
---


# PGETNEXTELEMENT callback function
The Bluetooth 
  <b>SdpGetNextElement</b> function is used to iterate through the entries found in an SDP record
  stream.

## Syntax

```
PGETNEXTELEMENT Pgetnextelement;

void Pgetnextelement(
  PUCHAR Stream,
  ULONG StreamSize,
  PUCHAR CurrentElement,
  PUCHAR *NextElement,
  PULONG NextElementSize
)
{...}
```

## Parameters

`Stream`

Pointer to the SDP record stream to iterate through.

`StreamSize`

An unsigned long integer that indicates the size of the SDP stream.

`CurrentElement`

A pointer to the currently selected entry in the SDP stream. This parameter can take a <b>NULL</b>
     value.

`*NextElement`

A pointer to an unsigned character variable that receives the address of the next entry in the SDP
     container stream.

`NextElementSize`

A pointer to an unsigned long integer variable that receives the size of the next entry in the SDP
     container stream.


## Return Value

None

## Remarks

The 
    <b>SdpGetNextElement</b> function operates directly on unparsed streams and does not require the caller to
    convert from a stream representation of the SDP record to a tree-based representation.

The 
    <b>SdpGetNextElement</b> function iterates through the primary entries of a container stream but does not
    iterate through any sub-entries of the given entry. To iterate through the sub-entries call 
    <b>SdpGetNextElement</b> iteratively using the 
    <i>NextElement</i> parameter obtained from the previous call.

Calling this function with the 
    <i>CurrentElement</i> parameter set to <b>NULL</b> returns the first entry in the container stream.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_parse_interface.md">
    BTHDDI_SDP_PARSE_INTERFACE</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later.  |
| **Target Platform** | Desktop |
| **Header** | bthsdpddi.h (include BthSdpddi.h) |
| **IRQL** | "<= PASSIVE_LEVEL" |

## See Also

<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_parse_interface.md">BTHDDI_SDP_PARSE_INTERFACE</a>