---
UID: NE:d3dkmdt._DXGK_CHILD_DEVICE_HPD_AWARENESS
title: "_DXGK_CHILD_DEVICE_HPD_AWARENESS"
author: windows-driver-content
description: The DXGK_CHILD_DEVICE_HPD_AWARENESS enumeration is used to describe the hot plug capabilities of a child device of a display adapter.
old-location: display\dxgk_child_device_hpd_awareness.htm
old-project: display
ms.assetid: daef347a-26d4-46cf-82b4-a5852fe49b71
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDXGK_CHILD_DEVICE_HPD_AWARENESS, DXGK_CHILD_DEVICE_HPD_AWARENESS, DXGK_CHILD_DEVICE_HPD_AWARENESS enumeration [Display Devices], DmEnums_1d5801e8-cb03-4409-a037-b25242176eea.xml, HpdAwarenessAlwaysConnected, HpdAwarenessInterruptible, HpdAwarenessNone, HpdAwarenessPolled, HpdAwarenessUninitialized, PDXGK_CHILD_DEVICE_HPD_AWARENESS, PDXGK_CHILD_DEVICE_HPD_AWARENESS enumeration pointer [Display Devices], _DXGK_CHILD_DEVICE_HPD_AWARENESS, d3dkmdt/DXGK_CHILD_DEVICE_HPD_AWARENESS, d3dkmdt/HpdAwarenessAlwaysConnected, d3dkmdt/HpdAwarenessInterruptible, d3dkmdt/HpdAwarenessNone, d3dkmdt/HpdAwarenessPolled, d3dkmdt/HpdAwarenessUninitialized, d3dkmdt/PDXGK_CHILD_DEVICE_HPD_AWARENESS, display.dxgk_child_device_hpd_awareness"
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
-	DXGK_CHILD_DEVICE_HPD_AWARENESS
product: Windows
targetos: Windows
req.typenames: DXGK_CHILD_DEVICE_HPD_AWARENESS, *PDXGK_CHILD_DEVICE_HPD_AWARENESS
---

# _DXGK_CHILD_DEVICE_HPD_AWARENESS Enumeration
The DXGK_CHILD_DEVICE_HPD_AWARENESS enumeration is used to describe the hot plug capabilities of a child device of a display adapter.

## Syntax
````
typedef enum _DXGK_CHILD_DEVICE_HPD_AWARENESS { 
  HpdAwarenessUninitialized    = 0,
  HpdAwarenessAlwaysConnected  = 1,
  HpdAwarenessNone             = 2,
  HpdAwarenessPolled           = 3,
  HpdAwarenessInterruptible    = 4
} DXGK_CHILD_DEVICE_HPD_AWARENESS, *PDXGK_CHILD_DEVICE_HPD_AWARENESS;
````

## Constants

<table>
            
                <tr>
                    <td>HpdAwarenessUninitialized</td>
                    <td>Indicates that a variable of type DXGK_CHILD_DEVICE_HPD_AWARENESS has not yet been assigned a meaningful value.</td>
                </tr>
            
                <tr>
                    <td>HpdAwarenessAlwaysConnected</td>
                    <td>Indicates that the child device is always connected; that is, it does not serve as a connector for external devices.</td>
                </tr>
            
                <tr>
                    <td>HpdAwarenessNone</td>
                    <td>Reserved for system use. You should not use this value.</td>
                </tr>
            
                <tr>
                    <td>HpdAwarenessPolled</td>
                    <td>Indicates that the display miniport driver is able to determine whether an external device is connected to the child device by polling the child device.</td>
                </tr>
            
                <tr>
                    <td>HpdAwarenessInterruptible</td>
                    <td>Indicates that the child device is able to generate an interrupt when an external device is connected or disconnected.</td>
                </tr>
</table>

## Remarks

The <b>ChildCapabilities</b> member of a <a href="..\dispmprt\ns-dispmprt-_dxgk_child_descriptor.md">DXGK_CHILD_DESCRIPTOR</a> structure is a <a href="..\dispmprt\ns-dispmprt-_dxgk_child_capabilities.md">DXGK_CHILD_CAPABILITIES</a> structure. The <b>HpdAwareness</b> member of a <b>DXGK_CHILD_DEVICE_HPD_AWARENESS</b> structure is a <b>DXGK_CHILD_CAPABILITIES</b>  structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

## See Also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a>