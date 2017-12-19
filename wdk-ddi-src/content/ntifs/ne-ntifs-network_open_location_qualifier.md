---
UID: NE.ntifs.NETWORK_OPEN_LOCATION_QUALIFIER
title: NETWORK_OPEN_LOCATION_QUALIFIER
author: windows-driver-content
description: The NETWORK_OPEN_LOCATION_QUALIFIER enumeration type contains values that identify the kind of location restriction to attach to a file.
old-location: ifsk\network_open_location_qualifier.htm
old-project: ifsk
ms.assetid: 7762bf83-82cc-4eef-9699-d093a8c2b986
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NETWORK_OPEN_LOCATION_QUALIFIER, NETWORK_OPEN_LOCATION_QUALIFIER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This enumeration type is available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NETWORK_OPEN_LOCATION_QUALIFIER
req.alt-loc: ntifs.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# NETWORK_OPEN_LOCATION_QUALIFIER enumeration



## -description
The NETWORK_OPEN_LOCATION_QUALIFIER enumeration type contains values that identify the kind of location restriction to attach to a file.



## -syntax

````
typedef enum  { 
  NetworkOpenLocationAny       = 0,
  NetworkOpenLocationRemote    = 1,
  NetworkOpenLocationLoopback  = 2
} NETWORK_OPEN_LOCATION_QUALIFIER;
````


## -enum-fields

### -field NetworkOpenLocationAny

Indicates that the file has no location restrictions. That is, a caller can open the file whether it resides remotely or locally. 


### -field NetworkOpenLocationRemote

Indicates that the file is restricted to only opening remotely. That is, a caller can only open the file if it resides on a different computer from the computer that the caller resides on. 


### -field NetworkOpenLocationLoopback

Indicates that the file is restricted to only opening locally. That is, a caller can only open the file if it resides on the same computer as the caller. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
This enumeration type is available starting with Windows Vista. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>