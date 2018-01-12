---
UID: NS:windot11._DOT11_WFD_DEVICE_TYPE
title: _DOT11_WFD_DEVICE_TYPE
author: windows-driver-content
description: The DOT11_WFD_DEVICE_TYPE structure is used to specify primary and secondary device types.
old-location: netvista\dot11_wfd_device_type.htm
old-project: netvista
ms.assetid: 4AE7C35B-D2EA-4987-8195-EDD472C39681
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _DOT11_WFD_DEVICE_TYPE, DOT11_WFD_DEVICE_TYPE, *PDOT11_WFD_DEVICE_TYPE
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
req.alt-api: DOT11_WFD_DEVICE_TYPE
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
req.typenames: DOT11_WFD_DEVICE_TYPE, *PDOT11_WFD_DEVICE_TYPE
req.product: Windows 10 or later.
---

# _DOT11_WFD_DEVICE_TYPE structure



## -description

## -syntax

````
typedef struct _DOT11_WFD_DEVICE_TYPE {
  USHORT   CategoryID;
  USHORT   SubCategoryID;
  UCHAR    OUI[4];
} DOT11_WFD_DEVICE_TYPE, *PDOT11_WFD_DEVICE_TYPE;
````


## -struct-fields

### -field CategoryID

The identifier of the main type category.


### -field SubCategoryID

The identifier of the type subcategory.


### -field OUI[4]

The Organizationally Unique Identifier (OUI) assigned to a device.


## -remarks
The <b>DOT11_WFD_DEVICE_TYPE</b> data is provided in host byte-ordering. The miniport may need to convert the data to an ordering appropriate for inclusion in Peer-to-Peer Information Elements.


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