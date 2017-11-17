---
UID: NS.61883._GET_UNIT_CAPABILITIES
title: GET_UNIT_CAPABILITIES
author: windows-driver-content
description: The GET_UNIT_CAPABILITIES structure is used in conjunction with the Av61883_GetUnitInfo request to retrieve unit information about a device's capabilities.
old-location: ieee\get_unit_capabilities.htm
ms.assetid: 7fe180c2-cf0b-4658-86e3-fed5e270db8c
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: IEEE
req.header: 61883.h
req.include-header: 61883.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GET_UNIT_CAPABILITIES
req.alt-loc: 61883.h
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
ms.keywords: GET_UNIT_CAPABILITIES, GET_UNIT_CAPABILITIES, *PGET_UNIT_CAPABILITIES
---

# GET_UNIT_CAPABILITIES structure



## -description
<p>The GET_UNIT_CAPABILITIES structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536983">Av61883_GetUnitInfo</a> request to retrieve unit information about a device's capabilities. </p>


## -syntax

````
typedef struct _GET_UNIT_CAPABILITIES {
  ULONG NumOutputPlugs;
  ULONG NumInputPlugs;
  ULONG MaxDataRate;
  ULONG CTSFlags;
  ULONG HardwareFlags;
} GET_UNIT_CAPABILITIES, *PGET_UNIT_CAPABILITIES;
````


## -struct-fields
<dl>

### -field <b>NumOutputPlugs</b>

<dd>
<p>The number of output plugs supported by the device.</p>
</dd>

### -field <b>NumInputPlugs</b>

<dd>
<p>The number of input plugs supported by the device.</p>
</dd>

### -field <b>MaxDataRate</b>

<dd>
<p>The maximum data rate of the device. Can be one of the following:</p>
<p>CMP_SPEED_S100</p>
<p>CMP_SPEED_S200</p>
<p>CMP_SPEED_S400</p>
</dd>

### -field <b>CTSFlags</b>

<dd>
<p>A bitmask that identifies the command and transaction sets supported by the device. For example, if <b>CTSFlags</b> is 0001, the device supports Audio Video Control (AV/C). If <b>CTSFlags</b> is 4000, the device supports a vendor-unique CTS. Most devices that support multiple command and transaction sets report each CTS value in a separate Configuration ROM unit directory entry, so typically only one bit is set at a time.</p>
</dd>

### -field <b>HardwareFlags</b>

<dd>
<p>If the AV_HOST_DMA_DOUBLE_BUFFERING_ENABLED flag is set, and the request level is SET_UNIT_INFO_ISOCH_PARAMS, then a size limit is imposed on members <b>RX_NumPackets</b> and <b>TX_NumPackets</b> of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538921">UNIT_ISOCH_PARAMS</a> structure. These members, when multiplied by the packet size, must be less than or equal to 64 KB. For example, <b>Rx_NumPackets * PacketSize </b>must be less than or equal to 64 KB. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>61883.h (include 61883.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536983">Av61883_GetUnitInfo</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20GET_UNIT_CAPABILITIES structure%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
