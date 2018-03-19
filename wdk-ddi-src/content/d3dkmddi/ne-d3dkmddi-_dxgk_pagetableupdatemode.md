---
UID: NE:d3dkmddi._DXGK_PAGETABLEUPDATEMODE
title: "_DXGK_PAGETABLEUPDATEMODE"
author: windows-driver-content
description: DXGK_PAGETABLEUPDATEMODE is used as part of a DxgkDdiBuildPagingBuffer operation to indicate which member of the related DXGK_PAGETABLEUPDATEADDRESS structure contains the address of the page table to update.
old-location: display\dxgk_pagetableupdatemode.htm
old-project: display
ms.assetid: E7C823B1-457E-4B86-B44B-DC5BD48CF98E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_PAGETABLEUPDATEMODE, DXGK_PAGETABLEUPDATEMODE enumeration [Display Devices], DXGK_PAGETABLEUPDATE_CPU_VIRTUAL, DXGK_PAGETABLEUPDATE_GPU_PHYSICAL, DXGK_PAGETABLEUPDATE_GPU_VIRTUAL, _DXGK_PAGETABLEUPDATEMODE, d3dkmddi/DXGK_PAGETABLEUPDATEMODE, d3dkmddi/DXGK_PAGETABLEUPDATE_CPU_VIRTUAL, d3dkmddi/DXGK_PAGETABLEUPDATE_GPU_PHYSICAL, d3dkmddi/DXGK_PAGETABLEUPDATE_GPU_VIRTUAL, display.dxgk_pagetableupdatemode
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_PAGETABLEUPDATEMODE
product: Windows
targetos: Windows
req.typenames: DXGK_PAGETABLEUPDATEMODE
---

# _DXGK_PAGETABLEUPDATEMODE Enumeration
<b>DXGK_PAGETABLEUPDATEMODE</b> is used as part of a <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a> operation to indicate which member of the related <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_pagetableupdateaddress.md">DXGK_PAGETABLEUPDATEADDRESS</a> structure contains the address of the page table to update.

## Syntax
````
typedef enum _DXGK_PAGETABLEUPDATEMODE { 
  DXGK_PAGETABLEUPDATE_CPU_VIRTUAL,
  DXGK_PAGETABLEUPDATE_GPU_VIRTUAL,
  DXGK_PAGETABLEUPDATE_GPU_PHYSICAL
} DXGK_PAGETABLEUPDATEMODE;
````

## Constants

<table>
            
                <tr>
                    <td>DXGK_PAGETABLEUPDATE_CPU_VIRTUAL</td>
                    <td>Indicates that the address of the page table to update is in the <b>CpuVirtual</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_pagetableupdateaddress.md">DXGK_PAGETABLEUPDATEADDRESS</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXGK_PAGETABLEUPDATE_GPU_VIRTUAL</td>
                    <td>Indicates that the address of the page table to update is in the <b>GpuVirtual</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_pagetableupdateaddress.md">DXGK_PAGETABLEUPDATEADDRESS</a> structure.</td>
                </tr>
            
                <tr>
                    <td>DXGK_PAGETABLEUPDATE_GPU_PHYSICAL</td>
                    <td>Indicates that the address of the page table to update is in the <b>GpuPhysical</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_pagetableupdateaddress.md">DXGK_PAGETABLEUPDATEADDRESS</a> structure.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_pagetableupdateaddress.md">DXGK_PAGETABLEUPDATEADDRESS</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a>