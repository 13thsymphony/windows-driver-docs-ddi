---
UID: NF.wdfdevice.WDF_DEVICE_PNP_CAPABILITIES_INIT
title: WDF_DEVICE_PNP_CAPABILITIES_INIT function
author: windows-driver-content
description: The WDF_DEVICE_PNP_CAPABILITIES_INIT function initializes a WDF_DEVICE_PNP_CAPABILITIES structure.
old-location: wdf\wdf_device_pnp_capabilities_init.htm
old-project: wdf
ms.assetid: 5ae60715-ba51-4814-ae34-34967cdbab78
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WDF_DEVICE_PNP_CAPABILITIES_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_DEVICE_PNP_CAPABILITIES_INIT
req.alt-loc: wdfdevice.h
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
req.product: Windows 10 or later.
---

# WDF_DEVICE_PNP_CAPABILITIES_INIT function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_DEVICE_PNP_CAPABILITIES_INIT</b> function initializes a <a href="wdf.wdf_device_pnp_capabilities">WDF_DEVICE_PNP_CAPABILITIES</a> structure.



## -syntax

````
VOID WDF_DEVICE_PNP_CAPABILITIES_INIT(
  _Out_ PWDF_DEVICE_PNP_CAPABILITIES Caps
);
````


## -parameters

### -param Caps [out]

A pointer to a driver-supplied <a href="wdf.wdf_device_pnp_capabilities">WDF_DEVICE_PNP_CAPABILITIES</a> structure.


## -returns
None


## -remarks
The <b>WDF_DEVICE_PNP_CAPABILITIES_INIT</b> function zeros the specified <a href="wdf.wdf_device_pnp_capabilities">WDF_DEVICE_PNP_CAPABILITIES</a> structure, sets the structure's <b>Size</b> member, and sets other members to default values.

For a code example that uses <b>WDF_DEVICE_PNP_CAPABILITIES_INIT</b>, see <a href="wdf.wdfdevicesetpnpcapabilities">WdfDeviceSetPnpCapabilities</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>