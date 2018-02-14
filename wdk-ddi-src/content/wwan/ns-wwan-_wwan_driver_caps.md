---
UID: NS:wwan._WWAN_DRIVER_CAPS
title: "_WWAN_DRIVER_CAPS"
author: windows-driver-content
description: The WWAN_DRIVER_CAPS structure represents the capabilities of the miniport driver.
old-location: netvista\wwan_driver_caps.htm
old-project: netvista
ms.assetid: c0696ac6-d35e-402a-8cb5-d4f23b3b8072
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WWAN_DRIVER_CAPS, wwan/WWAN_DRIVER_CAPS, PWWAN_DRIVER_CAPS, _WWAN_DRIVER_CAPS, *PWWAN_DRIVER_CAPS, netvista.wwan_driver_caps, WwanRef_6770f91c-0fe7-49a9-97cb-6af43e5b5727.xml, wwan/PWWAN_DRIVER_CAPS, WWAN_DRIVER_CAPS structure [Network Drivers Starting with Windows Vista], PWWAN_DRIVER_CAPS structure pointer [Network Drivers Starting with Windows Vista]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
-	WWAN_DRIVER_CAPS
product: Windows
targetos: Windows
req.typenames: WWAN_DRIVER_CAPS, *PWWAN_DRIVER_CAPS
req.product: Windows 10 or later.
---

# _WWAN_DRIVER_CAPS structure
The WWAN_DRIVER_CAPS structure represents the capabilities of the miniport driver.

## Syntax
````
typedef struct _WWAN_DRIVER_CAPS {
  ULONG ulMajorVersion;
  ULONG ulMinorVersion;
  ULONG ulDriverCaps;
} WWAN_DRIVER_CAPS, *PWWAN_DRIVER_CAPS;
````

## Members


`ulDriverCaps`

This member is reserved for future use. Miniport drivers should set this member to the value in
     the following table.
     





#### WWAN_DRIVER_CAPS_NONE

The miniport driver has no special capabilities.

`ulMajorVersion`

The major version of the MB driver model that the miniport driver supports. Miniport drivers
     should set this member to WWAN_MAJOR_VERSION.

`ulMinorVersion`

The minor version of the MB driver model that the miniport driver supports. Miniport drivers
     should set this member to WWAN_MINOR_VERSION.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_driver_caps.md">NDIS_WWAN_DRIVER_CAPS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_DRIVER_CAPS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>