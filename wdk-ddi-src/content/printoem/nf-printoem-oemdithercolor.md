---
UID: NF:printoem.OEMDitherColor
title: OEMDitherColor function
author: windows-driver-content
description: The OEMDitherColor function requests the device to create a brush dithered against a device palette.
old-location: print\oemdithercolor.htm
old-project: print
ms.assetid: bf8c2140-8917-42af-86bf-c2f25b0c42b7
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: OEMDitherColor, print_unidrv-pscript_rendering_e220d80f-83d4-4f4a-9fdc-ca25b48dd718.xml, OEMDitherColor function [Print Devices], print.oemdithercolor, printoem/OEMDitherColor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	OEMDitherColor
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMDitherColor function
The <code>OEMDitherColor</code> function requests the device to create a brush dithered against a device palette.

## Syntax

````
ULONG APIENTRY OEMDitherColor(
   DHPDEV dhpdev,
   ULONG  iMode,
   ULONG  rgbColor,
   ULONG  *pulDither
);
````

## Parameters

`dhpdev`



`iMode`



`rgbColor`



`pulDither`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |