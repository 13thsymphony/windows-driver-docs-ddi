---
UID: NE:bthxddi._BTHX_SCO_SUPPORT
title: _BTHX_SCO_SUPPORT
author: windows-driver-content
description: The BTHX_SCO_SUPPORT enumeration lists the different types of SCO supported by the transport driver.
old-location: bltooth\bthx_sco_support.htm
old-project: bltooth
ms.assetid: A9B303C7-868D-47EB-8279-9F655F58630C
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _BTHX_SCO_SUPPORT, *PBTHX_SCO_SUPPORT, BTHX_SCO_SUPPORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: bthxddi.h
req.include-header: BthXDDI.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BTHX_SCO_SUPPORT
req.alt-loc: BthXDDI.h
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
req.typenames: *PBTHX_SCO_SUPPORT, BTHX_SCO_SUPPORT
---

# _BTHX_SCO_SUPPORT enumeration



## -description
The BTHX_SCO_SUPPORT enumeration lists the different types of SCO supported by the transport driver.



## -syntax

````
typedef enum _BTHX_SCO_SUPPORT { 
  ScoSupportNone       = 0,
  ScoSupportHCI        = 1,
  ScoSupportHCIBypass  = 2
} BTHX_SCO_SUPPORT;
````


## -enum-fields

### -field ScoSupportNone

SCO is not supported.


### -field ScoSupportHCI

SCO data passes through the HCI layer (stack).


### -field ScoSupportHCIBypass

SCO data does not pass through the HCI layer but through a sideband mechanism like an I2S channel.


## -remarks
Upon starting, the Bluetooth stack will query the transport driver for its capabilities by sending the <a href="..\bthxddi\ni-bthxddi-ioctl_bthx_query_capabilities.md">IOCTL_BTHX_QUERY_CAPABILITIES</a> IOCTL.

The output buffer of this IOCTL is defined by the <a href="..\bthxddi\ns-bthxddi-_bthx_capabilities.md">BTHX_CAPABILITIES</a> structure which contains the 
BTHX_SCO_SUPPORT structure.

The transport driver must specify <b>ScoSupportHCIBypass</b>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Versions: Supported starting with  Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>BthXDDI.h (include BthXDDI.h)</dt>
</dl>
</td>
</tr>
</table>