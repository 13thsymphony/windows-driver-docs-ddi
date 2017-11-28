---
UID: NE.wwan._WWAN_PCO_TYPE
title: WWAN_PCO_TYPE
author: windows-driver-content
description: The WWAN_PCO_TYPE enumeration indicates whether the header of a PCO structure is partial, meaning only a subset of the complete PCO value from the network is being passed up to the host.
old-location: netvista\wwan_pco_type.htm
old-project: netvista
ms.assetid: 0AD10F14-EBDB-45F8-A435-1D0A6D6FEFFF
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WUDF_WORKITEM_CONFIG, WUDF_WORKITEM_CONFIG, *PWUDF_WORKITEM_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WWAN_PCO_TYPE
req.alt-loc: wwan.h
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
req.iface: 
req.product: Windows 10 or later.
---

# WWAN_PCO_TYPE enumeration



## -description
<p>The <b>WWAN_PCO_TYPE</b> enumeration indicates whether the header of a PCO structure is partial, meaning only a subset of the complete PCO value from the network is being passed up to the host. This type will help the upper edge logic know the validity of the header of the PCO structure.</p>


## -syntax

````
typedef enum _WWAN_PCO_TYPE { 
  WwanPcoTypeComplete  = 0,
  WwanPcoTypePartial
} WWAN_PCO_TYPE;
````


## -enum-fields
<dl>

### -field <a id="WwanPcoTypeComplete"></a><a id="wwanpcotypecomplete"></a><a id="WWANPCOTYPECOMPLETE"></a><b>WwanPcoTypeComplete</b>

<dd>
<p>Specifies that the complete PCO structure will be passed up as received from the network and the header realistically reflects the protocol in octet 3 of the PCO structure, defined in the 3GPP TS24.008 spec. To see the full PCO structure, see <a href="..\wwan\ns-wwan--wwan-pco-value.md">WWAN_PCO_VALUE</a>.</p>
</dd>

### -field <a id="WwanPcoTypePartial"></a><a id="wwanpcotypepartial"></a><a id="WWANPCOTYPEPARTIAL"></a><b>WwanPcoTypePartial</b>

<dd>
<p>Specifies that the modem will only be passing up a subset of PCO structures that it received from the network. The header matches the 3GPP TS24.008 specification for the PCO structure, as shown on <b>WWAN_PCO_VALUE</b>, but the “Configuration protocol” of octet 3 may not be valid.</p>
</dd>
</dl>

## -remarks
<p>Currently, in Windows 10, version 1709, some modems can only pass up operator specific PCO elements. These will have the type is set as <b>WwanPcoTypePartial</b>, and the header should have the following:</p>

<p>The OS will not check if the PCO data is valid and leaves the validation to the MO application.</p>

<p>Currently, in Windows 10, version 1709, some modems can only pass up operator specific PCO elements. These will have the type is set as <b>WwanPcoTypePartial</b>, and the header should have the following:</p>

<p>The OS will not check if the PCO data is valid and leaves the validation to the MO application.</p>

<p>Currently, in Windows 10, version 1709, some modems can only pass up operator specific PCO elements. These will have the type is set as <b>WwanPcoTypePartial</b>, and the header should have the following:</p>

<p>The OS will not check if the PCO data is valid and leaves the validation to the MO application.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Windows 10, version 1709</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wwan.h (include Wwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wwan\ns-wwan--wwan-pco-value.md">WWAN_PCO_VALUE</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-protocol-configuration-operations--pco-">MB Protocol Configuration Operations (PCO)</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PCO_TYPE enumeration%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
