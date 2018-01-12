---
UID: NE:pointofservicecommontypes.DriverMagneticStripeReaderAuthenticationLevel
title: DriverMagneticStripeReaderAuthenticationLevel
author: windows-driver-content
description: This enumeration defines the levels of magnetic stripe reader (MSR) authentication support.
old-location: pos\magneticstripereaderauthenticationlevel_handheld_blue_autogen.htm
old-project: pos
ms.assetid: 779e750a-70c6-41f3-b680-a9fe833014b5
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: DriverMagneticStripeReaderAuthenticationLevel, DriverMagneticStripeReaderAuthenticationLevel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pointofservicecommontypes.h
req.include-header: Pointofservicecommontypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DriverMagneticStripeReaderAuthenticationLevel
req.alt-loc: pointofservicecommontypes.h
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
req.typenames: DriverMagneticStripeReaderAuthenticationLevel
---

# DriverMagneticStripeReaderAuthenticationLevel enumeration



## -description
This enumeration defines the levels of magnetic stripe reader (MSR) authentication support.



## -syntax

````
typedef enum _DriverMagneticStripeReaderAuthenticationLevel { 
  NotSupported  = 0,
  Optional      = 1,
  Required      = 2
} DriverMagneticStripeReaderAuthenticationLevel;
````


## -enum-fields

### -field NotSupported

Does not support authentication.


### -field Optional

Supports authentication, but does not require it.


### -field Required

Requires authentication.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Pointofservicecommontypes.h (include Pointofservicecommontypes.h)</dt>
</dl>
</td>
</tr>
</table>