---
UID: NE:pointofservicecommontypes.DriverMagneticStripeReaderAuthenticationLevel
title: DriverMagneticStripeReaderAuthenticationLevel
author: windows-driver-content
description: This enumeration defines the levels of magnetic stripe reader (MSR) authentication support.
old-location: pos\magneticstripereaderauthenticationlevel_handheld_blue_autogen.htm
old-project: pos
ms.assetid: 779e750a-70c6-41f3-b680-a9fe833014b5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: Required, Optional, DriverMagneticStripeReaderAuthenticationLevel enumeration, pos.magneticstripereaderauthenticationlevel_handheld_blue_autogen, pointofservicecommontypes/NotSupported, pointofservicecommontypes/Optional, pointofservicecommontypes/DriverMagneticStripeReaderAuthenticationLevel, pointofservicecommontypes/Required, NotSupported, DriverMagneticStripeReaderAuthenticationLevel
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pointofservicecommontypes.h
apiname:
-	DriverMagneticStripeReaderAuthenticationLevel
product: Windows
targetos: Windows
req.typenames: DriverMagneticStripeReaderAuthenticationLevel
---

# DriverMagneticStripeReaderAuthenticationLevel Enumeration
This enumeration defines the levels of magnetic stripe reader (MSR) authentication support.

## Syntax
````
typedef enum _DriverMagneticStripeReaderAuthenticationLevel { 
  NotSupported  = 0,
  Optional      = 1,
  Required      = 2
} DriverMagneticStripeReaderAuthenticationLevel;
````

## Constants

<table>
            
                <tr>
                    <td>NotSupported</td>
                    <td>Does not support authentication.</td>
                </tr>
            
                <tr>
                    <td>Optional</td>
                    <td>Supports authentication, but does not require it.</td>
                </tr>
            
                <tr>
                    <td>Required</td>
                    <td>Requires authentication.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | pointofservicecommontypes.h (include Pointofservicecommontypes.h) |