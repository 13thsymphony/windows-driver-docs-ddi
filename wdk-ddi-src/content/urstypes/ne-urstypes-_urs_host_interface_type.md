---
UID: NE.urstypes._URS_HOST_INTERFACE_TYPE
title: _URS_HOST_INTERFACE_TYPE
author: windows-driver-content
description: Defines values for the various types of USB host controllers.
old-location: buses\urs_host_interface_type.htm
old-project: usbref
ms.assetid: E019CCED-3511-4B7B-B6C9-09FF31B0547A
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _URS_HOST_INTERFACE_TYPE, URS_HOST_INTERFACE_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: urstypes.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.alt-api: URS_HOST_INTERFACE_TYPE
req.alt-loc: urstypes.h
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

# _URS_HOST_INTERFACE_TYPE enumeration



## -description
Defines values for the various types of USB host controllers.



## -syntax

````
typedef enum _URS_HOST_INTERFACE_TYPE { 
  UrsHostInterfaceTypeEhci   = 0,
  UrsHostInterfaceTypeXhci,
  UrsHostInterfaceTypeOther
} URS_HOST_INTERFACE_TYPE;
````


## -enum-fields

### -field UrsHostInterfaceTypeEhci

Indicates an EHCI host controller.


### -field UrsHostInterfaceTypeXhci

Indicates an xHCI host controller.


### -field UrsHostInterfaceTypeOther

Indicates a generic host controller.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.15

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Urstypes.h (include Urscx.h)</dt>
</dl>
</td>
</tr>
</table>