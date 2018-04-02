---
UID: NE:dispmprt._DXGK_CHILD_DEVICE_TYPE
title: "_DXGK_CHILD_DEVICE_TYPE"
author: windows-driver-content
description: The DXGK_CHILD_DEVICE_TYPE enumeration is used to indicate the type of a child device of the display adapter.
old-location: display\dxgk_child_device_type.htm
old-project: display
ms.assetid: b16ba776-a6b2-46d0-9b6f-18ea17cf4fce
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDXGK_CHILD_DEVICE_TYPE, DXGK_CHILD_DEVICE_TYPE, DXGK_CHILD_DEVICE_TYPE enumeration [Display Devices], DmEnums_afd3654c-ffb4-49d6-ba59-235148e59d2c.xml, PDXGK_CHILD_DEVICE_TYPE, PDXGK_CHILD_DEVICE_TYPE enumeration pointer [Display Devices], TypeIntegratedDisplay, TypeOther, TypeUninitialized, TypeVideoOutput, _DXGK_CHILD_DEVICE_TYPE, display.dxgk_child_device_type, dispmprt/DXGK_CHILD_DEVICE_TYPE, dispmprt/PDXGK_CHILD_DEVICE_TYPE, dispmprt/TypeIntegratedDisplay, dispmprt/TypeOther, dispmprt/TypeUninitialized, dispmprt/TypeVideoOutput"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
-	dispmprt.h
api_name:
-	DXGK_CHILD_DEVICE_TYPE
product: Windows
targetos: Windows
req.typenames: DXGK_CHILD_DEVICE_TYPE, *PDXGK_CHILD_DEVICE_TYPE
---

# _DXGK_CHILD_DEVICE_TYPE Enumeration
The DXGK_CHILD_DEVICE_TYPE enumeration is used to indicate the type of a child device of the display adapter.

## Syntax
```
typedef enum _DXGK_CHILD_DEVICE_TYPE {
  TypeUninitialized      ,
  TypeVideoOutput        ,
  TypeOther              ,
  TypeIntegratedDisplay
} DXGK_CHILD_DEVICE_TYPE, *PDXGK_CHILD_DEVICE_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>TypeUninitialized</td>
                    <td>Indicates that a variable of type DXGK_CHILD_DEVICE_TYPE has not yet been assigned a meaningful value.</td>
                </tr>
            
                <tr>
                    <td>TypeVideoOutput</td>
                    <td>Indicates that the child device is a video output. A video output is the circuitry on the display adapter that supplies a video signal to an external or integrated monitor (or other display device). Note that monitors, integrated LCD panels, and other devices that actually display an image are not considered child devices of the display adapter.</td>
                </tr>
            
                <tr>
                    <td>TypeOther</td>
                    <td>Indicates that the child device is not a video output. TV tuners, crossbar switches, and MPEG2 codecs are examples of child devices that are not video outputs.</td>
                </tr>
            
                <tr>
                    <td>TypeIntegratedDisplay</td>
                    <td>Type indicating that this target is permanently connected to an integrated display.</td>
                </tr>
</table>

## Remarks

The <b>ChildDeviceType</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a> structure is a DXGK_CHILD_DEVICE_TYPE value.

For more information about child devices of display adapters, see <a href="https://msdn.microsoft.com/9fd20e1a-db98-4571-8fc4-6d33fd0e2f16">Child Devices of the Display Adapter</a> and <a href="https://msdn.microsoft.com/3bec2117-aef4-41fc-b88a-0081c7c9fe3d">Enumerating Child Devices of a Display Adapter</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | dispmprt.h (include Dispmprt.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561001">DXGK_CHILD_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/eb1a0df0-6239-4d82-8477-7dd015f80b6e">DxgkDdiQueryChildRelations</a>