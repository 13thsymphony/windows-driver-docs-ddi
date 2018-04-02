---
UID: NF:printoem.OEMIcmCreateColorTransform
title: OEMIcmCreateColorTransform function
author: windows-driver-content
description: The OEMIcmCreateColorTransform function creates an ICM color transform.
old-location: print\oemicmcreatecolortransform.htm
old-project: print
ms.assetid: 995fdac4-e958-4eed-ba3a-7be0349dec59
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMIcmCreateColorTransform, OEMIcmCreateColorTransform function [Print Devices], print.oemicmcreatecolortransform, print_unidrv-pscript_rendering_102b853d-78f9-4e06-a3e5-c76f55caa42e.xml, printoem/OEMIcmCreateColorTransform
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
-	OEMIcmCreateColorTransform
product:
- Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMIcmCreateColorTransform function
The <code>OEMIcmCreateColorTransform</code> function creates an ICM color transform.

## Syntax

```
HANDLE OEMIcmCreateColorTransform(
  DHPDEV           dhpdev,
  LPLOGCOLORSPACEW pLogColorSpace,
  PVOID            pvSourceProfile,
  ULONG            cjSourceProfile,
  PVOID            pvDestProfile,
  ULONG            cjDestProfile,
  PVOID            pvTargetProfile,
  ULONG            cjTargetProfile,
  DWORD            dwReserved
);
```

## Parameters

`dhpdev`



`pLogColorSpace`



`pvSourceProfile`



`cjSourceProfile`



`pvDestProfile`



`cjDestProfile`



`pvTargetProfile`



`cjTargetProfile`



`dwReserved`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |