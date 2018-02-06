---
UID: NS:wdfdriver._WDF_DRIVER_VERSION_AVAILABLE_PARAMS
title: "_WDF_DRIVER_VERSION_AVAILABLE_PARAMS"
author: windows-driver-content
description: The WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure specifies major and minor version numbers for the Kernel-Mode Driver Framework's library.
old-location: wdf\wdf_driver_version_available_params.htm
old-project: wdf
ms.assetid: 7f5192ac-aea0-4e63-b2f9-1d51e00bbf03
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: "*PWDF_DRIVER_VERSION_AVAILABLE_PARAMS, wdf.wdf_driver_version_available_params, PWDF_DRIVER_VERSION_AVAILABLE_PARAMS structure pointer, wdfdriver/WDF_DRIVER_VERSION_AVAILABLE_PARAMS, WDF_DRIVER_VERSION_AVAILABLE_PARAMS, kmdf.wdf_driver_version_available_params, wdfdriver/PWDF_DRIVER_VERSION_AVAILABLE_PARAMS, PWDF_DRIVER_VERSION_AVAILABLE_PARAMS, DFDriverObjectRef_dea9dee4-b36b-4672-89cb-bbffe0a78f3b.xml, WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure, _WDF_DRIVER_VERSION_AVAILABLE_PARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfdriver.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	wdfdriver.h
apiname:
-	WDF_DRIVER_VERSION_AVAILABLE_PARAMS
product: Windows
targetos: Windows
req.typenames: WDF_DRIVER_VERSION_AVAILABLE_PARAMS, *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS
req.product: Windows 10 or later.
---

# _WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure
<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure specifies major and minor version numbers for the Kernel-Mode Driver Framework's library.

## Syntax
````
typedef struct _WDF_DRIVER_VERSION_AVAILABLE_PARAMS {
  ULONG Size;
  ULONG MajorVersion;
  ULONG MinorVersion;
} WDF_DRIVER_VERSION_AVAILABLE_PARAMS, *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS;
````

## Members


`MajorVersion`

A numeric value that represents the Kernel-Mode Driver Framework library's major version number.

`MinorVersion`

A numeric value that represents the Kernel-Mode Driver Framework library's minor version number.

`Size`

The size, in bytes, of this structure.

## Remarks
The WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure is used as input to the <a href="..\wdfdriver\nf-wdfdriver-wdfdriverisversionavailable.md">WdfDriverIsVersionAvailable</a> method. Drivers should call <a href="..\wdfdriver\nf-wdfdriver-wdf_driver_version_available_params_init.md">WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT</a> to initialize this structure before calling <b>WdfDriverIsVersionAvailable</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdriver.h (include Wdf.h) |

## See Also

<a href="..\wdfdriver\nf-wdfdriver-wdfdriverisversionavailable.md">WdfDriverIsVersionAvailable</a>

<a href="..\wdfdriver\nf-wdfdriver-wdf_driver_version_available_params_init.md">WDF_DRIVER_VERSION_AVAILABLE_PARAMS_INIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DRIVER_VERSION_AVAILABLE_PARAMS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>