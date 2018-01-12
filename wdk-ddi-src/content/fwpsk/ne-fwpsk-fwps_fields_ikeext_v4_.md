---
UID: NE:fwpsk.FWPS_FIELDS_IKEEXT_V4_
title: FWPS_FIELDS_IKEEXT_V4_
author: windows-driver-content
description: The FWPS_FIELDS_IKEEXT_V4 enumeration type specifies the data field identifiers for the FWPS_LAYER_IKEEXT_V4 run-time filtering layer.
old-location: netvista\fwps_fields_ikeext_v4.htm
old-project: netvista
ms.assetid: 5d2a7eda-343b-4713-9481-6f54f713811f
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: FWPS_FIELDS_IKEEXT_V4_, FWPS_FIELDS_IKEEXT_V4
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Unless otherwise noted, supported starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_FIELDS_IKEEXT_V4
req.alt-loc: fwpsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: FWPS_FIELDS_IKEEXT_V4
---

# FWPS_FIELDS_IKEEXT_V4_ enumeration



## -description
The FWPS_FIELDS_IKEEXT_V4 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_IKEEXT_V4 
  <a href="netvista.run_time_filtering_layer_identifiers">run-time filtering layer</a>.



## -syntax

````
typedef enum FWPS_FIELDS_IKEEXT_V4_ { 
  FWPS_FIELD_IKEEXT_V4_IP_LOCAL_ADDRESS,
  FWPS_FIELD_IKEEXT_V4_IP_REMOTE_ADDRESS,
  FWPS_FIELD_IKEEXT_V4_IP_LOCAL_INTERFACE,
#if (NTDDI_VERSION >= NTDDI_WIN7)
  FWPS_FIELD_IKEEXT_V4_PROFILE_ID,
#endif 
  FWPS_FIELD_IKEEXT_V4_MAX
} FWPS_FIELDS_IKEEXT_V4;
````


## -enum-fields

### -field FWPS_FIELD_IKEEXT_V4_IP_LOCAL_ADDRESS

The local IP address.


### -field FWPS_FIELD_IKEEXT_V4_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_IKEEXT_V4_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>) for the network interface associated with the local IP address.


### -field FWPS_FIELD_IKEEXT_V4_PROFILE_ID

The profile identifier (network category) of the network interface. The possible network category
     values are: public (1), private (2), or domain (3).
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_IKEEXT_V4_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Unless otherwise noted, supported starting with Windows Vista.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_FIELDS_IKEEXT_V4 enumeration%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

