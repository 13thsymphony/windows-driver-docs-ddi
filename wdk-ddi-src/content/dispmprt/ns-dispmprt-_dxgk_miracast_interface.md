---
UID: NS:dispmprt._DXGK_MIRACAST_INTERFACE
title: "_DXGK_MIRACAST_INTERFACE"
author: windows-driver-content
description: Contains pointers to functions in the Wireless display (Miracast) interface that the display miniport driver implements to create, destroy, query, and control Miracast device resources.
old-location: display\dxgk_miracast_display_interface.htm
old-project: display
ms.assetid: 39DCDA28-D32F-4755-91FB-0D42822D7B54
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PDXGK_MIRACAST_DISPLAY_INTERFACE, DXGK_MIRACAST_DISPLAY_INTERFACE, DXGK_MIRACAST_DISPLAY_INTERFACE structure [Display Devices], PDXGK_MIRACAST_DISPLAY_INTERFACE, PDXGK_MIRACAST_DISPLAY_INTERFACE structure pointer [Display Devices], _DXGK_MIRACAST_INTERFACE, display.dxgk_miracast_display_interface, dispmprt/DXGK_MIRACAST_DISPLAY_INTERFACE, dispmprt/PDXGK_MIRACAST_DISPLAY_INTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	Dispmprt.h
api_name:
-	DXGK_MIRACAST_DISPLAY_INTERFACE
product: Windows
targetos: Windows
req.typenames: DXGK_MIRACAST_DISPLAY_INTERFACE, *PDXGK_MIRACAST_DISPLAY_INTERFACE
---

# _DXGK_MIRACAST_INTERFACE structure
Contains pointers to functions in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn344651">Wireless display (Miracast) interface</a> that the display miniport driver implements to create, destroy, query, and control Miracast device resources.

## Syntax
```
typedef struct _DXGK_MIRACAST_INTERFACE {
  USHORT                             Size;
  USHORT                             Version;
  PVOID                              Context;
  PINTERFACE_REFERENCE               InterfaceReference;
  PINTERFACE_DEREFERENCE             InterfaceDereference;
  DXGKDDI_MIRACAST_QUERY_CAPS        DxgkDdiMiracastQueryCaps;
  DXGKDDI_MIRACAST_CREATE_CONTEXT    DxgkDdiMiracastCreateContext;
  DXGKDDI_MIRACAST_HANDLE_IO_CONTROL DxgkDdiMiracastIoControl;
  DXGKDDI_MIRACAST_DESTROY_CONTEXT   DxgkDdiMiracastDestroyContext;
} *PDXGK_MIRACAST_DISPLAY_INTERFACE, DXGK_MIRACAST_DISPLAY_INTERFACE;
```

## Members


`Size`

The size, in bytes, of this structure.

`Version`

The version number of the Miracast interface. Version number constants are defined in Dispmprt.h (for example, DXGK_MIRACAST_DISPLAY_INTERFACE_VERSION_1).

`Context`

A pointer to a context that is provided by the display miniport driver.

`InterfaceReference`

A pointer to an interface reference function that is implemented by the display miniport driver.

`InterfaceDereference`

A pointer to an interface dereference function that is implemented by the display miniport driver.

`DxgkDdiMiracastQueryCaps`

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/C10CAA33-C407-4183-9090-B9D78B07CD12">DxgkDdiMiracastQueryCaps</a> function.

`DxgkDdiMiracastCreateContext`

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/BFF952CE-AA0F-4622-BBFC-946A45859FB7">DxgkDdiMiracastCreateContext</a> function.

`DxgkDdiMiracastIoControl`

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/83E817C3-A30D-4597-A490-C4FB93A78FCE">DxgkDdiMiracastIoControl</a> function.

`DxgkDdiMiracastDestroyContext`

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/2DEEB379-C9E8-45E4-920D-D94F8C27A4EF">DxgkDdiMiracastDestroyContext</a> function.

## Remarks
When the graphics adapter is started, the Microsoft DirectX graphics kernel subsystem calls the display miniport driver's <a href="https://msdn.microsoft.com/d8255f36-be3a-4b19-ac8d-8748ac9b6a24">DxgkDdiQueryInterface</a> function to retrieve the interface.

If the driver does not support Miracast displays, it should fail the query for this interface.

If the driver supports Miracast displays, then it must also support High-bandwidth Digital Content Protection (HDCP).

For more info on how to use the Miracast interface, see <a href="https://msdn.microsoft.com/D67CAC4F-0409-4E8D-A31A-78C3EB473556">WDDM display miniport driver tasks to support Miracast wireless displays</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | dispmprt.h (include Dispmprt.h) |

## See Also

<a href="https://msdn.microsoft.com/BFF952CE-AA0F-4622-BBFC-946A45859FB7">DxgkDdiMiracastCreateContext</a>



<a href="https://msdn.microsoft.com/2DEEB379-C9E8-45E4-920D-D94F8C27A4EF">DxgkDdiMiracastDestroyContext</a>



<a href="https://msdn.microsoft.com/83E817C3-A30D-4597-A490-C4FB93A78FCE">DxgkDdiMiracastIoControl</a>



<a href="https://msdn.microsoft.com/C10CAA33-C407-4183-9090-B9D78B07CD12">DxgkDdiMiracastQueryCaps</a>



<a href="https://msdn.microsoft.com/d8255f36-be3a-4b19-ac8d-8748ac9b6a24">DxgkDdiQueryInterface</a>