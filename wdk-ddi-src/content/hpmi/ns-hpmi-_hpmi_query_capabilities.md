---
UID: NS:hpmi._HPMI_QUERY_CAPABILITIES
title: "_HPMI_QUERY_CAPABILITIES"
author: windows-driver-content
description: The HPMI_QUERY_CAPABILITIES structure is used to query HPMI capabilities.
old-location: powermeter\hpmi_query_capabilities.htm
old-project: powermeter
ms.assetid: 9DEEB369-8B9E-40AA-9531-6B8138E5668F
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PHPMI_QUERY_CAPABILITIES, HPMI_QUERY_CAPABILITIES, HPMI_QUERY_CAPABILITIES structure [Power Metering and Budgeting Devices], PHPMI_QUERY_CAPABILITIES, PHPMI_QUERY_CAPABILITIES structure pointer [Power Metering and Budgeting Devices], _HPMI_QUERY_CAPABILITIES, hpmi/HPMI_QUERY_CAPABILITIES, hpmi/PHPMI_QUERY_CAPABILITIES, powermeter.hpmi_query_capabilities"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hpmi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of the Windows operating systems.
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
-	hpmi.h
api_name:
-	HPMI_QUERY_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: HPMI_QUERY_CAPABILITIES, *PHPMI_QUERY_CAPABILITIES
---

# _HPMI_QUERY_CAPABILITIES structure
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>HPMI_QUERY_CAPABILITIES</b> structure is used to query HPMI capabilities.

## Syntax
````
typedef struct _HPMI_QUERY_CAPABILITIES {
  ULONG Version;
} HPMI_QUERY_CAPABILITIES, *PHPMI_QUERY_CAPABILITIES;
````

## Members


`Version`

Set to HPMI_QUERY_CAPABILITIES_VERSION_1.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 10, version 1709 and later versions of the Windows operating systems. Available in Windows 10, version 1709 and later versions of the Windows operating systems. |
| **Header** | hpmi.h |

## See Also

<a href="https://msdn.microsoft.com/35934D6C-3FB4-4AD4-AA50-BD3A7790269F">hpmi.h</a>



<a href="..\hpmi\ns-hpmi-_hpmi_query_capabilities_response.md">HPMI_QUERY_CAPABILITIES_RESPONSE</a>



<a href="..\hpmi\ni-hpmi-ioctl_hpmi_query_capabilities.md">IOCTL_HPMI_QUERY_CAPABILITIES</a>