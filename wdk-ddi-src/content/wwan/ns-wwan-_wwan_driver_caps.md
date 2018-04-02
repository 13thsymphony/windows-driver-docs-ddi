---
UID: NS:wwan._WWAN_DRIVER_CAPS
title: "_WWAN_DRIVER_CAPS"
author: windows-driver-content
description: The WWAN_DRIVER_CAPS structure represents the capabilities of the miniport driver.
old-location: netvista\wwan_driver_caps.htm
old-project: netvista
ms.assetid: c0696ac6-d35e-402a-8cb5-d4f23b3b8072
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_DRIVER_CAPS, PWWAN_DRIVER_CAPS, PWWAN_DRIVER_CAPS structure pointer [Network Drivers Starting with Windows Vista], WWAN_DRIVER_CAPS, WWAN_DRIVER_CAPS structure [Network Drivers Starting with Windows Vista], WwanRef_6770f91c-0fe7-49a9-97cb-6af43e5b5727.xml, _WWAN_DRIVER_CAPS, netvista.wwan_driver_caps, wwan/PWWAN_DRIVER_CAPS, wwan/WWAN_DRIVER_CAPS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_DRIVER_CAPS
product: Windows
targetos: Windows
req.typenames: WWAN_DRIVER_CAPS, *PWWAN_DRIVER_CAPS
req.product: Windows 10 or later.
---

# _WWAN_DRIVER_CAPS structure
The WWAN_DRIVER_CAPS structure represents the capabilities of the miniport driver.

## Syntax
```
typedef struct _WWAN_DRIVER_CAPS {
  ULONG ulMajorVersion;
  ULONG ulMinorVersion;
  ULONG ulDriverCaps;
} *PWWAN_DRIVER_CAPS, WWAN_DRIVER_CAPS;
```

## Members


`ulMajorVersion`

The major version of the MB driver model that the miniport driver supports. Miniport drivers
     should set this member to WWAN_MAJOR_VERSION.

`ulMinorVersion`

The minor version of the MB driver model that the miniport driver supports. Miniport drivers
     should set this member to WWAN_MINOR_VERSION.

`ulDriverCaps`

This member is reserved for future use. Miniport drivers should set this member to the value in
     the following table.
     





#### WWAN_DRIVER_CAPS_NONE

The miniport driver has no special capabilities.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567908">NDIS_WWAN_DRIVER_CAPS</a>