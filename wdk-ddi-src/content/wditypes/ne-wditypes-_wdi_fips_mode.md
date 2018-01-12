---
UID: NE:wditypes._WDI_FIPS_MODE
title: _WDI_FIPS_MODE
author: windows-driver-content
description: The WDI_FIPS_MODE enumeration defines values that specify if FIPS mode is enabled or not.
old-location: netvista\wdi_fips_mode.htm
old-project: netvista
ms.assetid: 88EE4C63-C9D8-41D2-800E-9FFD5EF4962A
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _WDI_FIPS_MODE, WDI_FIPS_MODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_FIPS_MODE
req.alt-loc: wditypes.hpp
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
req.typenames: WDI_FIPS_MODE
req.product: Windows 10 or later.
---

# _WDI_FIPS_MODE enumeration



## -description
The 
  WDI_FIPS_MODE enumeration defines values that specify if FIPS mode is enabled or not.



## -syntax

````
typedef enum _WDI_FIPS_MODE { 
  WDI_FIPS_MODE_DISABLED  = 0,
  WDI_FIPS_MODE_ENABLED   = 1,
  WDI_FIPS_MODE_UNKNOWN   = 2
} WDI_FIPS_MODE;
````


## -enum-fields

### -field WDI_FIPS_MODE_DISABLED

FIPS mode is disabled.


### -field WDI_FIPS_MODE_ENABLED

FIPS mode is enabled.


### -field WDI_FIPS_MODE_UNKNOWN

Unknown.


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
Header

</th>
<td width="70%">
<dl>
<dt>Wditypes.hpp</dt>
</dl>
</td>
</tr>
</table>