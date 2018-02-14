---
UID: NE:d3dumddi.D3DDDI_COPY_FLAGS
title: D3DDDI_COPY_FLAGS
author: windows-driver-content
description: Specifies how to handle the existing contents of a resource during a copy or update operation of a region within that resource.
old-location: display\d3dddi_copy_flags.htm
old-project: display
ms.assetid: 6186dac4-4797-48f2-bb32-40a0d501bac7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDI_COPY_FLAGS enumeration [Display Devices], D3DDDI_COPY_FLAGS, D3DDDI_COPY_NO_OVERWRITE, D3DDDI_COPY_DISCARD, d3dumddi/D3DDDI_COPY_NO_OVERWRITE, d3dumddi/D3DDDI_COPY_DISCARD, d3dumddi/D3DDDI_COPY_FLAGS, display.d3dddi_copy_flags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	D3dumddi.h
apiname:
-	D3DDDI_COPY_FLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDI_COPY_FLAGS
---

# D3DDDI_COPY_FLAGS Enumeration
Specifies how to handle the existing contents of a resource during a copy or update operation of a region within that resource.

## Syntax
````
typedef enum D3DDDI_COPY_FLAGS { 
  D3DDDI_COPY_NO_OVERWRITE  = 0x00000001,
  D3DDDI_COPY_DISCARD       = 0x00000002
} D3DDDI_COPY_FLAGS;
````

## Constants

<table>
            
                <tr>
                    <td>D3DDDI_COPY_DISCARD</td>
                    <td>The user-mode display driver can discard previous contents of the entire resource. The driver can take advantage of this capability to optimize performance and memory usage.</td>
                </tr>
            
                <tr>
                    <td>D3DDDI_COPY_NO_OVERWRITE</td>
                    <td>The caller guarantees that the portion of the surface that is being written to with new data is not currently being referenced or accessed by any previous render operation. The driver can take advantage of this capability to optimize performance and memory usage.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dumddi.h (include D3dumddi.h) |