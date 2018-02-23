---
UID: NE:d3d10umddi.D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE
title: D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE
author: windows-driver-content
description: Specifies the type of Microsoft Direct3D authenticated channel.
old-location: display\d3d11_1ddi_authenticated_channel_type.htm
old-project: display
ms.assetid: da04ef5d-c3e4-4321-8cc8-e20763c5a7db
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE enumeration [Display Devices], display.d3d11_1ddi_authenticated_channel_type, d3d10umddi/D3D11_1DDI_AUTHENTICATED_CHANNEL_DRIVER_HARDWARE, D3D11_1DDI_AUTHENTICATED_CHANNEL_DRIVER_SOFTWARE, d3d10umddi/D3D11_1DDI_AUTHENTICATED_CHANNEL_DRIVER_SOFTWARE, d3d10umddi/D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE, D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE, D3D11_1DDI_AUTHENTICATED_CHANNEL_DRIVER_HARDWARE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE
---

# D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE Enumeration
Specifies the type of Microsoft Direct3D authenticated channel.

## Syntax
````
typedef enum D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE { 
  D3D11_1DDI_AUTHENTICATED_CHANNEL_DRIVER_SOFTWARE  = 2,
  D3D11_1DDI_AUTHENTICATED_CHANNEL_DRIVER_HARDWARE  = 3
} D3D11_1DDI_AUTHENTICATED_CHANNEL_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>D3D11_1DDI_AUTHENTICATED_CHANNEL_DRIVER_HARDWARE</td>
                    <td>Hardware driver channel. This channel provides communication with a driver that implements content protection mechanisms in the GPU hardware.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_AUTHENTICATED_CHANNEL_DRIVER_SOFTWARE</td>
                    <td>Software driver channel. This channel provides communication with a driver that implements content protection mechanisms in software.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |