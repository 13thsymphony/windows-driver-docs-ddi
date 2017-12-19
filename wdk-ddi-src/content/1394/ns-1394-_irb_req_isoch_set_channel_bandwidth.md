---
UID: NS.1394._IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH
title: _IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH
author: windows-driver-content
description: This structure contains the fields necessary for the Bus driver to carry out an IsochSetChannelBandwidth request.
old-location: ieee\irb_req_isoch_set_channel_bandwidth.htm
old-project: IEEE
ms.assetid: CBEB68C2-549F-4EB6-9AF4-4DCA6749F75D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH, IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH
req.alt-loc: 1394.h
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
---

# _IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH structure



## -description
This structure contains the fields necessary for the Bus driver to carry out an <b>IsochSetChannelBandwidth</b> request.



## -syntax

````
typedef struct _IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH {
  HANDLE hBandwidth;
  ULONG  nMaxBytesPerFrame;
  ULONG  nBandwidthUnitsRequired;
} IRB_REQ_ISOCH_SET_CHANNEL_BANDWIDTH;
````


## -struct-fields

### -field hBandwidth

Bandwidth handle to reset.


### -field nMaxBytesPerFrame

Specifies the new bandwidth for <b>hBandwidth</b>.


### -field nBandwidthUnitsRequired

Specifies a pre-calculated value.


## -remarks
This request does not require the caller to know the bandwidth that was allocated when a handle was generated. REQUEST_ISOCH_SET_CHANNEL_BANDWIDTH can be used to readjust the bandwidth on a bandwidth handle whose bytes per frame setting is unknown. Despite its name, this request does not involve isochronous channels in any way.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>1394.h</dt>
</dl>
</td>
</tr>
</table>