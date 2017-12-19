---
UID: NS.WINDOT11._DOT11_WFD_GROUP_START_PARAMETERS
title: _DOT11_WFD_GROUP_START_PARAMETERS
author: windows-driver-content
description: The DOT11_WFD_GROUP_START_PARAMETERS structure is included with an OID_DOT11_WFD_GROUP_START_PARAMETERS request. The structure contains startup parameters for a Group Owner (GO).
old-location: netvista\dot11_wfd_group_start_parameters.htm
old-project: NetVista
ms.assetid: DA17F7DB-E6E7-4934-8AAF-73800ABF1432
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _DOT11_WFD_GROUP_START_PARAMETERS, *PDOT11_WFD_GROUP_START_PARAMETERS, DOT11_WFD_GROUP_START_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with   Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_WFD_GROUP_START_PARAMETERS
req.alt-loc: Windot11.h
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

# _DOT11_WFD_GROUP_START_PARAMETERS structure



## -description

## -syntax

````
typedef struct _DOT11_WFD_GROUP_START_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_WFD_CHANNEL  AdvertisedOperatingChannel;
} DOT11_WFD_GROUP_START_PARAMETERS, *PDOT11_WFD_GROUP_START_PARAMETERS;
````


## -struct-fields

### -field Header

The type, revision, and size of the <b>DOT11_WFD_GROUP_START_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following.

<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_ GROUP_START_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_WFD_GROUP_START_PARAMETERS_REVISION_1</td>
</tr>
</table>
 


### -field AdvertisedOperatingChannel

The channel information originally sent to the Client in a GO Negotiation or Invitation exchange. This is the preferred channel for starting the group. The miniport must ensure regulatory compliance when starting the Group Owner.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with   Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Windot11.h (include Windot11.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451800">OID_DOT11_WFD_GROUP_START_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20DOT11_WFD_GROUP_START_PARAMETERS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

