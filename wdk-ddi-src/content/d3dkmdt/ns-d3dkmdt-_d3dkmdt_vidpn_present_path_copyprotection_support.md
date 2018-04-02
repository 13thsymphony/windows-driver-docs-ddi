---
UID: NS:d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT
title: "_D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT"
author: windows-driver-content
description: The D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT structure is used to indicate the types of copy protection that are supported by a particular VidPN present path.
old-location: display\d3dkmdt_vidpn_present_path_copyprotection_support.htm
old-project: display
ms.assetid: 2b0c7428-bc88-461c-ab72-daccf02606da
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT, D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT structure [Display Devices], DmStructs_01eb8f42-1ba1-46e3-9b56-99952e5fedbe.xml, _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT, d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT, display.d3dkmdt_vidpn_present_path_copyprotection_support
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT
---

# _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT structure
The D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT structure is used to indicate the types of copy protection that are supported by a particular VidPN present path.

## Syntax
```
typedef struct _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT {
  UINT  : 1  NoProtection;
  UINT  : 1  MacroVisionApsTrigger;
  UINT  : 1  MacroVisionFull;
  UINT  : 29 Reserved;
} D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT;
```

## Members


`NoProtection`

The path is not capable of providing any copy protection.

`MacroVisionApsTrigger`

The path is capable of providing Rovi (formerly Macrovision) analog protection support (APS).

`MacroVisionFull`

The path is capable of providing full Rovi (formerly Macrovision) copy protection.

`Reserved`

Reserved for future use.

## Remarks
The <b>CopyProtectionSupport</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546656">D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION</a> structure is a D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |