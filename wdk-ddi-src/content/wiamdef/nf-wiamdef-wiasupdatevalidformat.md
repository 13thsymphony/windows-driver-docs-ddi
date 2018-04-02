---
UID: NF:wiamdef.wiasUpdateValidFormat
title: wiasUpdateValidFormat function
author: windows-driver-content
description: The wiasUpdateValidFormat function updates the valid format of the property context for the current minidriver.
old-location: image\wiasupdatevalidformat.htm
old-project: image
ms.assetid: 04e66f34-3771-4b09-b546-f814e4b41906
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiasupdatevalidformat, wiamdef/wiasUpdateValidFormat, wiasFncs_dfbd0aa5-1c7c-4b4f-a1da-82176b36e914.xml, wiasUpdateValidFormat, wiasUpdateValidFormat function [Imaging Devices]
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
-	wiasUpdateValidFormat
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---


# wiasUpdateValidFormat function
The <b>wiasUpdateValidFormat</b> function updates the valid format of the property context for the current minidriver.

## Syntax

```
HRESULT wiasUpdateValidFormat(
  BYTE                 *pWiasContext,
  WIA_PROPERTY_CONTEXT *pContext,
  IWiaMiniDrv          *pIMiniDrv
);
```

## Parameters

`pWiasContext`

Pointer to a WIA item context.

`pContext`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552749">WIA_PROPERTY_CONTEXT</a> structure containing a property context.

`pIMiniDrv`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545027">IWiaMiniDrv Interface</a> of the current minidriver.


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552749">WIA_PROPERTY_CONTEXT</a>