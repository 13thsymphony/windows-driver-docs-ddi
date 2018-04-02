---
UID: NF:d3dkmthk.D3DKMTCreateBundleObject
title: D3DKMTCreateBundleObject function
author: windows-driver-content
description: Used to create a bundle object.
old-location: display\d3dkmtcreatebundleobject.htm
old-project: display
ms.assetid: c4d62ccf-606b-457e-a239-1b5189e42657
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTCreateBundleObject, D3DKMTCreateBundleObject method [Display Devices], d3dkmthk/D3DKMTCreateBundleObject, display.d3dkmtcreatebundleobject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3dkmthk.h
api_name:
-	D3DKMTCreateBundleObject
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTCreateBundleObject function
Used to create a bundle object.

## Syntax

```
NTSTATUS D3DKMTCreateBundleObject(

);
```

## Parameters

This function has no parameters.

## Return Value

Returns STATUS_SUCCESS if the call has been successfully completed.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | d3dkmthk.h |