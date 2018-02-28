---
UID: NF:d3dkmthk.D3DKMTChangeSurfacePointer
title: D3DKMTChangeSurfacePointer function
author: windows-driver-content
description: The D3DKMTChangeSurfacePointer function is for system use only.
old-location: display\d3dkmtchangesurfacepointer.htm
old-project: display
ms.assetid: 3db4e04b-2707-4eb1-a249-2714304246a8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMTChangeSurfacePointer, D3DKMTChangeSurfacePointer callback function [Display Devices], OpenGL_Functions_b34c37f3-53fc-4dd3-a73a-f21c3010e00b.xml, PFND3DKMT_CHANGESURFACEPOINTER, d3dkmthk/D3DKMTChangeSurfacePointer, display.d3dkmtchangesurfacepointer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Desktop
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
-	D3DKMTChangeSurfacePointer
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTChangeSurfacePointer function
The <b>D3DKMTChangeSurfacePointer</b> function is for system use only.

## Syntax

````
NTSTATUS APIENTRY D3DKMTChangeSurfacePointer(
  _In_ const D3DKMT_CHANGESURFACEPOINTER *pData
);
````

## Parameters

`D3DKMT_CHANGESURFACEPOINTER`

TBD


## Return Value

An opaque NTSTATUS value.

## Remarks

This function is for system use only.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmthk.h |
| **Library** | NtosKrnl.exe |