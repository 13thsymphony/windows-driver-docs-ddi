---
UID: NS:d3d10umddi.D3D11_1DDI_OMAC
title: D3D11_1DDI_OMAC
author: windows-driver-content
description: Contains a Message Authentication Code (MAC).
old-location: display\d3d11_1ddi_omac.htm
old-project: display
ms.assetid: 6807f32a-0e63-4603-abfb-b35d0d0d5f8c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDI_OMAC, D3D11_1DDI_OMAC structure [Display Devices], d3d10umddi/D3D11_1DDI_OMAC, display.d3d11_1ddi_omac
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_OMAC
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_OMAC
---

# D3D11_1DDI_OMAC structure
Contains a Message Authentication Code (MAC).

## Syntax
````
typedef struct D3D11_1DDI_OMAC {
  BYTE Omac[D3D_OMAC_SIZE];
} D3D11_1DDI_OMAC;
````

## Members


`Omac`

A byte array that contains the cryptographic MAC value of the message.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |