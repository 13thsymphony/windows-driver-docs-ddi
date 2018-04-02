---
UID: NC:bthsdpddi.PVALIDATESTREAM
title: PVALIDATESTREAM
author: windows-driver-content
description: The Bluetooth SdpValidateStream function is used to parse a raw SDP record and determine if it contains errors.
old-location: bltooth\sdpvalidatestream.htm
old-project: bltooth
ms.assetid: cd119590-b910-487f-b611-5ef59204a798
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PVALIDATESTREAM, SdpValidateStream, SdpValidateStream callback function [Bluetooth Devices], bltooth.sdpvalidatestream, bth_funcs_1ba1d0ff-b873-4a38-8c5d-71e8afa35861.xml, bthsdpddi/SdpValidateStream
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
-	BthSdpddi.h
api_name:
-	SdpValidateStream
product:
- Windows
targetos: Windows
req.typenames: BTH_VENDOR_SPECIFIC_COMMAND, *PBTH_VENDOR_SPECIFIC_COMMAND
---


# PVALIDATESTREAM callback function
The Bluetooth 
  <b>SdpValidateStream</b> function is used to parse a raw SDP record and determine if it contains
  errors.

## Syntax

```
PVALIDATESTREAM Pvalidatestream;

NTSTATUS Pvalidatestream(
  PUCHAR Stream,
  ULONG Size,
  PULONG_PTR ErrorByte
)
{...}
```

## Parameters

`Stream`

A pointer to the raw SDP stream to be validated.

`Size`

An unsigned long integer that indicates the size of the SDP stream to be validated.

`ErrorByte`

A pointer to a variable that receives the address of the first byte in the SDP record that
     contains an error. The address is absolute.


## Return Value

Possible return values include:


<dl>
<dt>STATUS_SUCCESS
      </dt>
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>

## Remarks

The 
    <b>SdpValidateStream</b> function does nothing on success. On failure, it pinpoints the location of the
    first error in the specified SDP record.

Bluetooth profile drivers should use this function to validate all SDP streams from external sources.
    Other SDP functions might not perform complete data validation.

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