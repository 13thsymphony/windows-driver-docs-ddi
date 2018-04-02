---
UID: NF:wiamdef.wiasGetRootItem
title: wiasGetRootItem function
author: windows-driver-content
description: The wiasGetRootItem function retrieves the root item context of a specified WIA item.
old-location: image\wiasgetrootitem.htm
old-project: image
ms.assetid: 09885782-2293-49a3-af48-6450dbc6a24e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiasgetrootitem, wiamdef/wiasGetRootItem, wiasFncs_4e991723-5462-456e-b56f-82a38e5cf556.xml, wiasGetRootItem, wiasGetRootItem function [Imaging Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
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
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Wiaservc.dll
api_name:
-	wiasGetRootItem
product:
- Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---


# wiasGetRootItem function
The <b>wiasGetRootItem</b> function retrieves the root item context of a specified WIA item.

## Syntax

```
HRESULT wiasGetRootItem(
  BYTE *pWiasContext,
  BYTE **ppWiasContext
);
```

## Parameters

`pWiasContext`

Pointer to a WIA item context.

`ppWiasContext`

Pointer to a memory location that receives the address of the WIA item's root item context.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | wiamdef.h (include Wiamdef.h) |
| **Library** | Wiaservc.lib |
| **DLL** | Wiaservc.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549243">wiasGetDrvItem</a>