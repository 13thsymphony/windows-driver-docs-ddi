---
UID: NC.bthsdpddi.PBYTESWAPUINT64
title: PBYTESWAPUINT64
author: windows-driver-content
description: The Bluetooth SdpByteSwapUint64 function is used to reverse the byte order of an unsigned 64-bit integer.
old-location: bltooth\sdpbyteswapuint64.htm
old-project: bltooth
ms.assetid: aa3c83fb-72fb-4709-8c5d-982814ddbcd0
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _BTH_VENDOR_SPECIFIC_COMMAND, *PBTH_VENDOR_SPECIFIC_COMMAND, BTH_VENDOR_SPECIFIC_COMMAND
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
req.alt-api: SdpByteSwapUint64
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
---

# PBYTESWAPUINT64 callback



## -description
The Bluetooth 
  <b>SdpByteSwapUint64</b> function is used to reverse the byte order of an unsigned 64-bit integer.


## -prototype

````
PBYTESWAPUINT64 SdpByteSwapUint64;

ULONGLONG SdpByteSwapUint64(
   ULONGLONG uint64
)
{ ... }
````


## -parameters

### -param uint64 

The unsigned 64-bit integer for which to reverse the byte order.

## -returns
<b>SdpByteSwapUint64</b> returns a converted unsigned 64-bit integer.

## -remarks
The 
    <b>SdpByteSwapUint64</b> function always reverses the byte order of the value passed in the 
    <i>uint64</i> parameter. Writers of Bluetooth device drivers can use this function to convert unsigned
    64-bit integer values from the byte order on the local computer to the byte order of the network that the
    computer is connected to.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="bltooth.bthddi_sdp_parse_interface">BTHDDI_SDP_PARSE_INTERFACE</a>.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Versions: Supported in Windows Vista, and later.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Sdplib.h (include BthSdpddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="bltooth.bthddi_sdp_parse_interface">BTHDDI_SDP_PARSE_INTERFACE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20PBYTESWAPUINT64 callback function%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
