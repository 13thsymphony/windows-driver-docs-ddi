---
UID: NF:aux_klib.AuxKlibGetImageExportDirectory
title: AuxKlibGetImageExportDirectory function
author: windows-driver-content
description: The AuxKlibGetImageExportDirectory routine returns an image module's export directory.
old-location: kernel\auxklibgetimageexportdirectory.htm
old-project: kernel
ms.assetid: 994ba853-88b6-4456-8fdb-3199979df05e
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: AuxKlibGetImageExportDirectory, AuxKlibGetImageExportDirectory routine [Kernel-Mode Driver Architecture], aux_klib/AuxKlibGetImageExportDirectory, aux_klib_266e4e59-eaf6-47a4-a5d0-27fc55426273.xml, kernel.auxklibgetimageexportdirectory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: aux_klib.h
req.include-header: Aux_klib.h
req.target-type: Universal
req.target-min-winverclnt: Supported starting with Windows 2000.
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
req.lib: Aux_Klib.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Aux_Klib.lib
-	Aux_Klib.dll
api_name:
-	AuxKlibGetImageExportDirectory
product: Windows
targetos: Windows
req.typenames: REPORT_ZONES_EXT_DATA, *PREPORT_ZONES_EXT_DATA
---


# AuxKlibGetImageExportDirectory function
The <b>AuxKlibGetImageExportDirectory</b> routine returns an image module's export directory.

## Syntax

```
PIMAGE_EXPORT_DIRECTORY AuxKlibGetImageExportDirectory(
  PVOID ImageBase
);
```

## Parameters

`ImageBase`

A pointer to the base of an image, which is obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff540639">AuxKlibQueryModuleInformation</a>.


## Return Value

<b>AuxKlibGetImageExportDirectory</b> returns a pointer to an <b>IMAGE_EXPORT_DIRECTORY</b> structure. This structure is defined in Ntimage.h, which is included in the Microsoft Windows Driver Kit (WDK).

## Remarks

Drivers must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff540636">AuxKlibInitialize</a> before calling <b>AuxKlibGetImageExportDirectory</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | aux_klib.h (include Aux_klib.h) |
| **Library** | Aux_Klib.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540639">AuxKlibQueryModuleInformation</a>