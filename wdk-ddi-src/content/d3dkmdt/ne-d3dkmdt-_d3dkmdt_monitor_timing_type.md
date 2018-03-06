---
UID: NE:d3dkmdt._D3DKMDT_MONITOR_TIMING_TYPE
title: "_D3DKMDT_MONITOR_TIMING_TYPE"
author: windows-driver-content
description: The D3DKMDT_MONITOR_TIMING_TYPE enumeration is reserved for system use. Do not use it in your driver.
old-location: display\d3dkmdt_monitor_timing_type.htm
old-project: display
ms.assetid: fb8a2c29-f41b-4701-bbc2-f0a8e6dadc11
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMDT_MONITOR_TIMING_TYPE, D3DKMDT_MONITOR_TIMING_TYPE enumeration [Display Devices], D3DKMDT_MTT_DEFAULTMONITORPROFILE, D3DKMDT_MTT_DETAILED, D3DKMDT_MTT_DRIVER, D3DKMDT_MTT_ESTABLISHED, D3DKMDT_MTT_EXTRASTANDARD, D3DKMDT_MTT_STANDARD, D3DKMDT_MTT_UNINITIALIZED, DmEnums_dd8c4653-6af5-420c-a74e-3b0d2201e84a.xml, _D3DKMDT_MONITOR_TIMING_TYPE, d3dkmdt/D3DKMDT_MONITOR_TIMING_TYPE, d3dkmdt/D3DKMDT_MTT_DEFAULTMONITORPROFILE, d3dkmdt/D3DKMDT_MTT_DETAILED, d3dkmdt/D3DKMDT_MTT_DRIVER, d3dkmdt/D3DKMDT_MTT_ESTABLISHED, d3dkmdt/D3DKMDT_MTT_EXTRASTANDARD, d3dkmdt/D3DKMDT_MTT_STANDARD, d3dkmdt/D3DKMDT_MTT_UNINITIALIZED, display.d3dkmdt_monitor_timing_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	D3DKMDT_MONITOR_TIMING_TYPE
product: Windows
targetos: Windows
req.typenames: D3DKMDT_MONITOR_TIMING_TYPE
---

# _D3DKMDT_MONITOR_TIMING_TYPE Enumeration
The D3DKMDT_MONITOR_TIMING_TYPE enumeration is reserved for system use. Do not use it in your driver.

## Syntax
````
typedef enum _D3DKMDT_MONITOR_TIMING_TYPE { 
  D3DKMDT_MTT_UNINITIALIZED          = 0,
  D3DKMDT_MTT_ESTABLISHED            = 1,
  D3DKMDT_MTT_STANDARD               = 2,
  D3DKMDT_MTT_EXTRASTANDARD          = 3,
  D3DKMDT_MTT_DETAILED               = 4,
  D3DKMDT_MTT_DEFAULTMONITORPROFILE  = 5,
  D3DKMDT_MTT_DRIVER                 = 6
} D3DKMDT_MONITOR_TIMING_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>D3DKMDT_MTT_DEFAULTMONITORPROFILE</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_MTT_DETAILED</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_MTT_DRIVER</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_MTT_ESTABLISHED</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_MTT_EXTRASTANDARD</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_MTT_STANDARD</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>D3DKMDT_MTT_UNINITIALIZED</td>
                    <td>Reserved for system use.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |