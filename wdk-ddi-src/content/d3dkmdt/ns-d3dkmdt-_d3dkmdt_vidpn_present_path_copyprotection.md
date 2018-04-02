---
UID: NS:d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION
title: "_D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION"
author: windows-driver-content
description: The D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure contains information about the copy protection that is supported (as well as the copy protection that is currently active) on a particular VidPN present path.
old-location: display\d3dkmdt_vidpn_present_path_copyprotection.htm
old-project: display
ms.assetid: 661e70c6-d99e-4c5a-ad88-3dd854747de4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION, D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure [Display Devices], DmStructs_512b61d6-627d-4423-93ba-0f28ac340e51.xml, _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION, d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION, display.d3dkmdt_vidpn_present_path_copyprotection
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
-	D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION
---

# _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure
The D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure contains information about the copy protection that is supported (as well as the copy protection that is currently active) on a particular VidPN present path.

## Syntax
```
typedef struct _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION {
  D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE    CopyProtectionType;
  UINT                                              APSTriggerBits;
  BYTE                                              OEMCopyProtection[D3DKMDT_MACROVISION_OEMCOPYPROTECTION_SIZE];
  D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT CopyProtectionSupport;
} D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION;
```

## Members


`CopyProtectionType`

A value from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546692">D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE</a> enumeration that indicates the type of copy protection that is active on the path.

`APSTriggerBits`

A value that describes copy protection for an OEM device. A value of 0 indicates no copy protection, and values of 1, 2, and 3 indicate low, medium, and high levels of copy protection, respectively. Values greater than 3 are not allowed.

`OEMCopyProtection`

Reserved for future use.

`CopyProtectionSupport`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff546677">D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT</a> structure that indicates the types of copy protection that are supported by the path.

## Remarks
The <b>CopyProtection</b> member of the  <a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a> structure is a D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |