---
UID: NE:d3dkmddi._DXGK_MEMORY_TRANSFER_DIRECTION
title: "_DXGK_MEMORY_TRANSFER_DIRECTION"
author: windows-driver-content
description: DXGK_MEMORY_TRANSFER_DIRECTION is used as part of an allocation transfer operation to specify the direction of the transfer.
old-location: display\dxgk_memory_transfer_direction.htm
old-project: display
ms.assetid: A45411DF-AD08-4349-A134-091343E7989E
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGK_MEMORY_TRANSFER_DIRECTION, DXGK_MEMORY_TRANSFER_LOCAL_TO_LOCAL, DXGK_MEMORY_TRANSFER_DIRECTION, _DXGK_MEMORY_TRANSFER_DIRECTION, d3dkmddi/DXGK_MEMORY_TRANSFER_SYSTEM_TO_LOCAL, DXGK_MEMORY_TRANSFER_LOCAL_TO_SYSTEM, d3dkmddi/DXGK_MEMORY_TRANSFER_LOCAL_TO_SYSTEM, d3dkmddi/DXGK_MEMORY_TRANSFER_LOCAL_TO_LOCAL, DXGK_MEMORY_TRANSFER_DIRECTION enumeration [Display Devices], DXGK_MEMORY_TRANSFER_SYSTEM_TO_LOCAL, display.dxgk_memory_transfer_direction
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_MEMORY_TRANSFER_DIRECTION
product: Windows
targetos: Windows
req.typenames: DXGK_MEMORY_TRANSFER_DIRECTION
---

# _DXGK_MEMORY_TRANSFER_DIRECTION Enumeration
<b>DXGK_MEMORY_TRANSFER_DIRECTION</b> is used as part of an allocation transfer operation to specify the direction of the transfer.

## Syntax
````
typedef enum _DXGK_MEMORY_TRANSFER_DIRECTION { 
  DXGK_MEMORY_TRANSFER_LOCAL_TO_SYSTEM  = 0,
  DXGK_MEMORY_TRANSFER_SYSTEM_TO_LOCAL  = 1,
  DXGK_MEMORY_TRANSFER_LOCAL_TO_LOCAL   = 2
} DXGK_MEMORY_TRANSFER_DIRECTION;
````

## Constants

<table>
            
                <tr>
                    <td>DXGK_MEMORY_TRANSFER_LOCAL_TO_LOCAL</td>
                    <td>Transfer from local GPU memory to local GPU memory.</td>
                </tr>
            
                <tr>
                    <td>DXGK_MEMORY_TRANSFER_LOCAL_TO_SYSTEM</td>
                    <td>Transfer from local GPU memory to system memory.</td>
                </tr>
            
                <tr>
                    <td>DXGK_MEMORY_TRANSFER_SYSTEM_TO_LOCAL</td>
                    <td>Transfer from system memory to local GPU memory.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |