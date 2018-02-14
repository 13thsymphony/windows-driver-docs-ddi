---
UID: NF:printoem.OEMTransparentBlt
title: OEMTransparentBlt function
author: windows-driver-content
description: The OEMTransparentBlt function provides bit-block transfer capabilities with transparency.
old-location: print\oemtransparentblt.htm
old-project: print
ms.assetid: 0ffd4759-cabe-4efe-a725-5b8ff26fda77
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: OEMTransparentBlt, OEMTransparentBlt function [Print Devices], print_unidrv-pscript_rendering_a02993f9-58d7-4a42-ad7b-be61bd6b265d.xml, print.oemtransparentblt, printoem/OEMTransparentBlt
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
-	OEMTransparentBlt
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMTransparentBlt function
The <code>OEMTransparentBlt</code> function provides bit-block transfer capabilities with transparency.

## Syntax

````
BOOL APIENTRY OEMTransparentBlt(
   SURFOBJ  *psoDst,
   STRFOBJ  *psoSrc,
   CLIPOBJ  *pco,
   XLATEOBJ *pxlo,
   RECTL    *prclDst,
   RECTL    *prclSrc,
   ULONG    iTransColor,
   ULONG    ulReserved
);
````

## Parameters

`psoDst`



`psoSrc`



`pco`



`pxlo`



`prclDst`



`prclSrc`



`iTransColor`



`ulReserved`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |