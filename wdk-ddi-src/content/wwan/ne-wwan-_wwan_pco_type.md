---
UID: NE:wwan._WWAN_PCO_TYPE
title: _WWAN_PCO_TYPE
author: windows-driver-content
description: The WWAN_PCO_TYPE enumeration indicates whether the header of a PCO structure is partial, meaning only a subset of the complete PCO value from the network is being passed up to the host.
old-location: netvista\wwan_pco_type.htm
old-project: netvista
ms.assetid: 0AD10F14-EBDB-45F8-A435-1D0A6D6FEFFF
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _WWAN_PCO_TYPE, *PWWAN_PCO_TYPE, WWAN_PCO_TYPE
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
req.typenames: *PWWAN_PCO_TYPE, WWAN_PCO_TYPE
req.product: Windows 10 or later.
---

# _WWAN_PCO_TYPE enumeration



## -description
The <b>WWAN_PCO_TYPE</b> enumeration indicates whether the header of a PCO structure is partial, meaning only a subset of the complete PCO value from the network is being passed up to the host. This type will help the upper edge logic know the validity of the header of the PCO structure.



## -syntax

````
typedef enum _WWAN_PCO_TYPE { 
  WwanPcoTypeComplete  = 0,
  WwanPcoTypePartial
} WWAN_PCO_TYPE;
````


## -enum-fields

### -field WwanPcoTypeComplete

Specifies that the complete PCO structure will be passed up as received from the network and the header realistically reflects the protocol in octet 3 of the PCO structure, defined in the 3GPP TS24.008 spec. To see the full PCO structure, see <a href="..\wwan\ns-wwan-_wwan_pco_value.md">WWAN_PCO_VALUE</a>.


### -field WwanPcoTypePartial

Specifies that the modem will only be passing up a subset of PCO structures that it received from the network. The header matches the 3GPP TS24.008 specification for the PCO structure, as shown on <b>WWAN_PCO_VALUE</b>, but the “Configuration protocol” of octet 3 may not be valid.


## -remarks
Currently, in Windows 10, version 1709, some modems can only pass up operator specific PCO elements. These will have the type is set as <b>WwanPcoTypePartial</b>, and the header should have the following:

The OS will not check if the PCO data is valid and leaves the validation to the MO application.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Windows 10, version 1709

</td>
</tr>
<tr>
<th width="30%">
Header

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
<a href="..\wwan\ns-wwan-_wwan_pco_value.md">WWAN_PCO_VALUE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/682C507C-5B2C-45E3-99D2-EEC68F8FC715">MB Protocol Configuration Operations (PCO)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PCO_TYPE enumeration%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

