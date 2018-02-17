---
UID: NE:urstypes._URS_HOST_INTERFACE_TYPE
title: "_URS_HOST_INTERFACE_TYPE"
author: windows-driver-content
description: Defines values for the various types of USB host controllers.
old-location: buses\urs_host_interface_type.htm
old-project: usbref
ms.assetid: E019CCED-3511-4B7B-B6C9-09FF31B0547A
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: urstypes/URS_HOST_INTERFACE_TYPE, UrsHostInterfaceTypeXhci, urstypes/UrsHostInterfaceTypeOther, URS_HOST_INTERFACE_TYPE enumeration [Buses], URS_HOST_INTERFACE_TYPE, _URS_HOST_INTERFACE_TYPE, UrsHostInterfaceTypeEhci, urstypes/UrsHostInterfaceTypeEhci, buses.urs_host_interface_type, UrsHostInterfaceTypeOther, urstypes/UrsHostInterfaceTypeXhci
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: urstypes.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
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
-	urstypes.h
apiname:
-	URS_HOST_INTERFACE_TYPE
product: Windows
targetos: Windows
req.typenames: URS_HOST_INTERFACE_TYPE
req.product: Windows 10 or later.
---

# _URS_HOST_INTERFACE_TYPE Enumeration
Defines values for the various types of USB host controllers.

## Syntax
````
typedef enum _URS_HOST_INTERFACE_TYPE { 
  UrsHostInterfaceTypeEhci   = 0,
  UrsHostInterfaceTypeXhci,
  UrsHostInterfaceTypeOther
} URS_HOST_INTERFACE_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>UrsHostInterfaceTypeEhci</td>
                    <td>Indicates an EHCI host controller.</td>
                </tr>
            
                <tr>
                    <td>UrsHostInterfaceTypeOther</td>
                    <td>Indicates a generic host controller.</td>
                </tr>
            
                <tr>
                    <td>UrsHostInterfaceTypeXhci</td>
                    <td>Indicates an xHCI host controller.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Minimum KMDF version** | 1.15 |
| **Header** | urstypes.h (include Urscx.h) |