---
UID: NS:d3dhal._DD_DXVERSION
title: "_DD_DXVERSION"
author: windows-driver-content
description: DirectX 8.0 and later versions only. DD_DXVERSION describes the current DirectX runtime version.
old-location: display\dd_dxversion.htm
old-project: display
ms.assetid: 72c22f76-c867-4924-b066-2ae4b25bfc43
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DD_DXVERSION, DD_DXVERSION structure [Display Devices], _DD_DXVERSION, d3dhal/DD_DXVERSION, d3dstrct_8955afcc-5fa5-493b-b291-69cd3b61ed8b.xml, display.dd_dxversion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	d3dhal.h
api_name:
-	DD_DXVERSION
product:
- Windows
targetos: Windows
req.typenames: DD_DXVERSION
---

# _DD_DXVERSION structure
DirectX 8.0 and later versions only.
   

DD_DXVERSION describes the current DirectX runtime version.

## Syntax
```
typedef struct _DD_DXVERSION {
  DD_GETDRIVERINFO2DATA gdi2;
  DWORD                 dwDXVersion;
  DWORD                 dwReserved;
} DD_DXVERSION;
```

## Members


`gdi2`

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551548">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data.

`dwDXVersion`

Specifies the version of DirectX. This member is set to DD_RUNTIME_VERSION, which is 0x00000700 for DirectX 7.0 and 0x00000800 for DirectX 8.0.

`dwReserved`

Reserved. Driver should not read or write.

## Remarks
This information is provided to a new driver (one that exposes <b>GetDriverInfo2</b>) for DX7 and DX8 applications.

The runtime provides a pointer to a DD_DXVERSION structure in the <b>lpvData</b> field of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a> data structure.

The <b>gdi2</b> member of DD_DXVERSION is used by the runtime with type D3DGDI2_TYPE_DXVERSION specified to notify the driver of the current DirectX runtime version being used by the application.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dhal.h (include D3dhal.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551548">DD_GETDRIVERINFO2DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a>