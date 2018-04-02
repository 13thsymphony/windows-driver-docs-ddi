---
UID: NS:pep_x._PEP_PPM_QUERY_LP_SETTINGS
title: "_PEP_PPM_QUERY_LP_SETTINGS"
author: windows-driver-content
description: The PEP_PPM_QUERY_LP_SETTINGS structure contains a kernel handle to the registry key that contains the power optimization settings that the platform extension plug-in (PEP) has defined for each power scenario.
old-location: kernel\pep_ppm_query_lp_settings.htm
old-project: kernel
ms.assetid: 69A8792B-954E-49AF-A306-25B94183E58A
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_PPM_QUERY_LP_SETTINGS, PEP_PPM_QUERY_LP_SETTINGS, PEP_PPM_QUERY_LP_SETTINGS structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_LP_SETTINGS, PPEP_PPM_QUERY_LP_SETTINGS structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_LP_SETTINGS, kernel.pep_ppm_query_lp_settings, pep_x/PEP_PPM_QUERY_LP_SETTINGS, pep_x/PPEP_PPM_QUERY_LP_SETTINGS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pepfx.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
-	pep_x.h
api_name:
-	PEP_PPM_QUERY_LP_SETTINGS
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_LP_SETTINGS, *PPEP_PPM_QUERY_LP_SETTINGS
---

# _PEP_PPM_QUERY_LP_SETTINGS structure
The <b>PEP_PPM_QUERY_LP_SETTINGS</b> structure contains a kernel handle to the registry key that contains the power optimization settings that the platform extension plug-in (PEP) has defined for each power scenario.

## Syntax
```
typedef struct _PEP_PPM_QUERY_LP_SETTINGS {
  HANDLE RegistryRoot;
} PEP_PPM_QUERY_LP_SETTINGS, *PPEP_PPM_QUERY_LP_SETTINGS;
```

## Members


`RegistryRoot`

[out] The kernel handle to the registry root that contains the settings for a platform power scenario. For more information, see Remarks.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt629122">PEP_NOTIFY_PPM_QUERY_LP_SETTINGS</a> notification. The <b>RegistryRoot</b> member contains an output value that the PEP writes to the structure in response to this notification.

The PEP can provide settings for certain key power scenarios such as full-screen video playback and connected standby that have unique characteristics that can benefit from specially tuned power policies that are different from the default settings used by Windows. The PEP loads the settings for such a power scenario into the registry and passes the registry key for these settings to the operating system.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pep_x.h (include Pepfx.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt629122">PEP_NOTIFY_PPM_QUERY_LP_SETTINGS</a>