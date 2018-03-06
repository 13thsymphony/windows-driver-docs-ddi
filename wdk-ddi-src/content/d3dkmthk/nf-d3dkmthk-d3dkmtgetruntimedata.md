---
UID: NF:d3dkmthk.D3DKMTGetRuntimeData
title: D3DKMTGetRuntimeData function
author: windows-driver-content
description: The D3DKMTGetRuntimeData function is for system use only.
old-location: display\d3dkmtgetruntimedata.htm
old-project: display
ms.assetid: a73ebde8-a1d5-4f97-8457-1f01244bb266
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTGetRuntimeData, D3DKMTGetRuntimeData callback function [Display Devices], OpenGL_Functions_c2273a4f-9a28-41b5-97c2-daa8eaa9f128.xml, PFND3DKMT_GETRUNTIMEDATA, d3dkmthk/D3DKMTGetRuntimeData, display.d3dkmtgetruntimedata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMTGetRuntimeData
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTGetRuntimeData function
The <b>D3DKMTGetRuntimeData</b> function is for system use only.

## Syntax

````
NTSTATUS APIENTRY D3DKMTGetRuntimeData(
  _Inout_ const D3DKMT_GETRUNTIMEDATA *pData
);
````

## Parameters

`D3DKMT_GETRUNTIMEDATA`

TBD


## Return Value

None

## Remarks

This function is reserved for system use.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h |
| **Library** | NtosKrnl.exe |