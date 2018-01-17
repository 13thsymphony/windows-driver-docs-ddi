---
UID: NC:bthsdpddi.PBYTESWAPUUID128
title: PBYTESWAPUUID128
author: windows-driver-content
description: The Bluetooth SdpByteSwapUuid128 function is used to reverse the byte order of a 128-bit universally unique identifier (UUID).
old-location: bltooth\sdpbyteswapuuid128.htm
old-project: bltooth
ms.assetid: 2598ebb3-1c9c-4ec1-b172-8c6d53415c9d
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _HFP_BYPASS_CODEC_ID_V1, HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: bthsdpddi.h
req.include-header: BthSdpddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SdpByteSwapUuid128
req.alt-loc: sdplib.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= PASSIVE_LEVEL
req.typenames: HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1
---

# PBYTESWAPUUID128 callback



## -description
The Bluetooth 
  <b>SdpByteSwapUuid128</b> function is used to reverse the byte order of a 128-bit universally unique
  identifier (UUID).



## -prototype

````
PBYTESWAPUUID128 SdpByteSwapUuid128;

void SdpByteSwapUuid128(
   GUID *pUuidFrom,
   GUID *pUuidTo
)
{ ... }
````


## -parameters

### -param pUuidFrom 

A pointer to the 128-bit GUID for which to reverse the byte order.


### -param pUuidTo 

A pointer to the converted 128-bit GUID.


## -returns
None


## -remarks
The 
    <b>SdpByteSwapUuid128</b> function always reverses the byte order of the value pointed to by the *
    <i>pUuidFrom</i> parameter. Writers of Bluetooth device drivers can use this function to convert 128-bit
    GUID values from the byte order on the local computer to the byte order of the network that the computer
    is connected to.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_parse_interface.md">BTHDDI_SDP_PARSE_INTERFACE</a>.


## -see-also
<dl>
<dt>
<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_parse_interface.md">BTHDDI_SDP_PARSE_INTERFACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20PBYTESWAPUUID128 callback function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

