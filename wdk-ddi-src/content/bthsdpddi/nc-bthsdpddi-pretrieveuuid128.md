---
UID : NC:bthsdpddi.PRETRIEVEUUID128
title : PRETRIEVEUUID128
author : windows-driver-content
description : The Bluetooth SdpRetrieveUuid128 function is used to copy an unaligned 128-bit universally unique identifier (UUID) from an SDP stream.
old-location : bltooth\sdpretrieveuuid128.htm
old-project : bltooth
ms.assetid : 0e317aea-3625-4511-94e1-355c476c0da6
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : bltooth.sdpretrieveuuid128, SdpRetrieveUuid128 callback function [Bluetooth Devices], SdpRetrieveUuid128, PRETRIEVEUUID128, PRETRIEVEUUID128, sdplib/SdpRetrieveUuid128, bth_funcs_a4149063-722b-45c0-a86b-ffce73b94b0d.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : bthsdpddi.h
req.include-header : BthSdpddi.h
req.target-type : Desktop
req.target-min-winverclnt : Versions: Supported in Windows Vista, and later.
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
req.irql : "<= PASSIVE_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PBTH_VENDOR_SPECIFIC_COMMAND, BTH_VENDOR_SPECIFIC_COMMAND"
---


# PRETRIEVEUUID128 callback function
The Bluetooth 
  <b>SdpRetrieveUuid128</b> function is used to copy an unaligned 128-bit universally unique identifier (UUID)
  from an SDP stream.

## Syntax

```
PRETRIEVEUUID128 Pretrieveuuid128;

void Pretrieveuuid128(
  PUCHAR Stream,
  GUID *uuid128
)
{...}
```

## Parameters

`Stream`

A pointer to an unaligned 128-bit UUID.

`*uuid128`




## Return Value

None

## Remarks

The 
    <b>SdpRetrieveUuid128</b> function does not search for the UUID to copy. The 
    <i>Stream</i> parameter must specify the exact address of the UUID to be extracted.

Some processor architectures require that values be aligned in memory and will generate an error if an
    attempt is made to access a misaligned value. SDP records are constructed without regard to processor
    alignment rules. When SDP records are stored in memory, they might contain elements that are misaligned
    according to local processor's alignment rules.

The 
    <b>SdpRetrieveUuid128</b> function safely copies UUIDs onto computers that have alignment requirements and
    efficiently copies UUIDs onto computers that do not have requirements. In addition, this function works
    on UUIDs that are aligned correctly.

This function has no effect on byte order.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <mshelp:link keywords="bltooth.bthddi_sdp_parse_interface" tabindex="0"><b>
    BTHDDI_SDP_PARSE_INTERFACE</b></mshelp:link> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bthsdpddi.h (include BthSdpddi.h) |
| **Library** |  |
| **IRQL** | <= PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_parse_interface.md">BTHDDI_SDP_PARSE_INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20PRETRIEVEUUID128 callback function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>