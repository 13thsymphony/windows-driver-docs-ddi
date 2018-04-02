---
UID: NF:wiamdef.wiasCreateLogInstance
title: wiasCreateLogInstance function
author: windows-driver-content
description: The wiasCreateLogInstance function creates an instance of a logging object.
old-location: image\wiascreateloginstance.htm
old-project: image
ms.assetid: 7a340187-51c5-4997-b4d0-5b89ea8e16c0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiascreateloginstance, wiamdef/wiasCreateLogInstance, wiasCreateLogInstance, wiasCreateLogInstance function [Imaging Devices], wiasFncs_f3d782d2-d11c-41bb-9d1e-d2619547dfda.xml
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
-	wiasCreateLogInstance
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---


# wiasCreateLogInstance function
The <b>wiasCreateLogInstance</b> function creates an instance of a logging object.

## Syntax

```
HRESULT wiasCreateLogInstance(
  BYTE      *pModuleHandle,
  IWiaLogEx **ppIWiaLogEx
);
```

## Parameters

`pModuleHandle`

Pointer to the module handle, which is used to filter output.

`ppIWiaLogEx`

Pointer to a memory location that receives the address of the logging interface.


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