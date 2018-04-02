---
UID: NF:d3dkmthk.D3DKMTSetDeviceLostSupport
title: D3DKMTSetDeviceLostSupport function
author: windows-driver-content
description: Used to indicate that the device has lost support.
old-location: display\d3dkmtsetdevicelostsupport.htm
old-project: display
ms.assetid: 9b7469cb-d489-4428-8167-91b26e1fa348
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMTSetDeviceLostSupport, D3DKMTSetDeviceLostSupport method [Display Devices], d3dkmthk/D3DKMTSetDeviceLostSupport, display.d3dkmtsetdevicelostsupport
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
-	D3DKMTSetDeviceLostSupport
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTSetDeviceLostSupport function
Used to indicate that the device has lost support.

## Syntax

```
NTSTATUS D3DKMTSetDeviceLostSupport(

);
```

## Parameters

This function has no parameters.

## Return Value

Returns STATUS_SUCCESS if completed successfully.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | d3dkmthk.h |