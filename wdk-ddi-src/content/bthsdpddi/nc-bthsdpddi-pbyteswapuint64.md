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
ms.keywords: BTH_VENDOR_SPECIFIC_COMMAND, BTH_VENDOR_SPECIFIC_COMMAND, *PBTH_VENDOR_SPECIFIC_COMMAND
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
req.iface: 
---

# PBYTESWAPUINT64 callback



## -description
<p>The Bluetooth 
  <b>SdpByteSwapUint64</b> function is used to reverse the byte order of an unsigned 64-bit integer.</p>


## -prototype

````
PBYTESWAPUINT64 SdpByteSwapUint64;

ULONGLONG SdpByteSwapUint64(
   ULONGLONG uint64
)
{ ... }
````


## -parameters
<dl>

### -param uint64 

<dd>
<p>The unsigned 64-bit integer for which to reverse the byte order.</p>
</dd>
</dl>

## -returns
<p><b>SdpByteSwapUint64</b> returns a converted unsigned 64-bit integer.</p>

## -remarks
<p>The 
    <b>SdpByteSwapUint64</b> function always reverses the byte order of the value passed in the 
    <i>uint64</i> parameter. Writers of Bluetooth device drivers can use this function to convert unsigned
    64-bit integer values from the byte order on the local computer to the byte order of the network that the
    computer is connected to.</p>

<p>Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="..\bthsdpddi\ns-bthsdpddi--bthddi-sdp-parse-interface.md">BTHDDI_SDP_PARSE_INTERFACE</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Versions: Supported in Windows Vista, and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Sdplib.h (include BthSdpddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\bthsdpddi\ns-bthsdpddi--bthddi-sdp-parse-interface.md">BTHDDI_SDP_PARSE_INTERFACE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20PBYTESWAPUINT64 callback function%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
