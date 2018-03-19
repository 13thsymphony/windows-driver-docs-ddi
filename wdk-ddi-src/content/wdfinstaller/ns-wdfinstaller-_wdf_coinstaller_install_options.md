---
UID: NS:wdfinstaller._WDF_COINSTALLER_INSTALL_OPTIONS
title: "_WDF_COINSTALLER_INSTALL_OPTIONS"
author: windows-driver-content
description: The WDF_COINSTALLER_INSTALL_OPTIONS structure contains installation options that a framework-based driver's installer can specify to the framework's co-installer.
old-location: wdf\wdf_coinstaller_install_options.htm
old-project: wdf
ms.assetid: be8867e4-42be-4f11-bf4b-1b0fd29daa06
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_COINSTALLER_INSTALL_OPTIONS, DFCoinstallerRef_71021229-7902-4d6a-a5f3-c9763860c7bf.xml, PWDF_COINSTALLER_INSTALL_OPTIONS, PWDF_COINSTALLER_INSTALL_OPTIONS structure pointer, WDF_COINSTALLER_INSTALL_OPTIONS, WDF_COINSTALLER_INSTALL_OPTIONS structure, _WDF_COINSTALLER_INSTALL_OPTIONS, kmdf.wdf_coinstaller_install_options, wdf.wdf_coinstaller_install_options, wdfinstaller/PWDF_COINSTALLER_INSTALL_OPTIONS, wdfinstaller/WDF_COINSTALLER_INSTALL_OPTIONS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfinstaller.h
req.include-header: Wdfinstaller.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
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
-	wdfinstaller.h
api_name:
-	WDF_COINSTALLER_INSTALL_OPTIONS
product: Windows
targetos: Windows
req.typenames: WDF_COINSTALLER_INSTALL_OPTIONS, *PWDF_COINSTALLER_INSTALL_OPTIONS
req.product: Windows 10 or later.
---

# _WDF_COINSTALLER_INSTALL_OPTIONS structure
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_COINSTALLER_INSTALL_OPTIONS</b> structure contains installation options that a framework-based driver's installer can specify to the framework's co-installer.

## Syntax
````
typedef struct _WDF_COINSTALLER_INSTALL_OPTIONS {
  ULONG Size;
  BOOL  ShowRebootPrompt;
} WDF_COINSTALLER_INSTALL_OPTIONS, *PWDF_COINSTALLER_INSTALL_OPTIONS;
````

## Members


`Size`

The size, in bytes, of this structure.

`ShowRebootPrompt`

A Boolean value. If this value is <b>TRUE</b>, and if the co-installer determines that the computer must be restarted to complete the driver installation, <a href="..\wdfinstaller\nf-wdfinstaller-wdfpredeviceinstallex.md">WdfPreDeviceInstallEx</a> informs the Plug and Play (PnP) manager, and the PnP manager prompts the user that a restart is necessary.  

If this value is <b>FALSE</b>, and if the co-installer determines that the computer must be restarted to complete the driver installation, <a href="..\wdfinstaller\nf-wdfinstaller-wdfpredeviceinstallex.md">WdfPreDeviceInstallEx</a> does not inform the PnP manager.

## Remarks
The <b>WDF_COINSTALLER_INSTALL_OPTIONS</b> structure is used as an input parameter to <a href="..\wdfinstaller\nf-wdfinstaller-wdfpredeviceinstallex.md">WdfPreDeviceInstallEx</a>.

Your installer should initialize the <b>WDF_COINSTALLER_INSTALL_OPTIONS</b> structure by calling <a href="..\wdfinstaller\nf-wdfinstaller-wdf_coinstaller_install_options_init.md">WDF_COINSTALLER_INSTALL_OPTIONS_INIT</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.9 |
| **Header** | wdfinstaller.h (include Wdfinstaller.h) |

## See Also

<a href="..\wdfinstaller\nf-wdfinstaller-wdf_coinstaller_install_options_init.md">WDF_COINSTALLER_INSTALL_OPTIONS_INIT</a>