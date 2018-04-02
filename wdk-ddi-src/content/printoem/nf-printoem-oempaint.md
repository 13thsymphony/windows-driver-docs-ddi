---
UID: NF:printoem.OEMPaint
title: OEMPaint function
author: windows-driver-content
description: The OEMPaint function is obsolete, and is no longer called by GDI in Windows 2000 and later. See DrvPaint.
old-location: print\oempaint.htm
old-project: print
ms.assetid: 4054c805-5307-41f4-a7ff-65743ae4be69
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMPaint, OEMPaint function [Print Devices], print.oempaint, print_unidrv-pscript_rendering_c9624a47-02fd-4eba-80d9-4035713ac594.xml, printoem/OEMPaint
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	printoem.h
api_name:
-	OEMPaint
product:
- Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMPaint function
The <code>OEMPaint</code> function is obsolete, and is no longer called by GDI in Windows 2000 and later. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff556256">DrvPaint</a>.

## Syntax

```
BOOL OEMPaint(
  SURFOBJ  *pso,
  CLIPOBJ  *pco,
  BRUSHOBJ *pbo,
  POINTL   *pptlBrushOrg,
  MIX      mix
);
```

## Parameters

`pso`



`pco`



`pbo`



`pptlBrushOrg`



`mix`




## Return Value

None

## Remarks

If you call into the core driver, cast the call using the <b>PFN_DrvPaint</b> function pointer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |