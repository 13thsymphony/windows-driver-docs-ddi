---
UID: NF:wiamdef.wiasSetPropertyAttributes
title: wiasSetPropertyAttributes function
author: windows-driver-content
description: The wiasSetPropertyAttributes function sets the access flags and valid values for a set of properties.
old-location: image\wiassetpropertyattributes.htm
old-project: image
ms.assetid: 210e69e7-b3b8-43b5-a0d3-f023c7256438
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiassetpropertyattributes, wiamdef/wiasSetPropertyAttributes, wiasFncs_630b9e1f-49f8-433e-b0f0-19e7e6c32460.xml, wiasSetPropertyAttributes, wiasSetPropertyAttributes function [Imaging Devices]
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
-	wiasSetPropertyAttributes
product:
- Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---


# wiasSetPropertyAttributes function
The <b>wiasSetPropertyAttributes </b>function sets the access flags and valid values for a set of properties.

## Syntax

```
HRESULT wiasSetPropertyAttributes(
  BYTE        *pWiasContext,
  LONG        cPropSpec,
  PROPSPEC    *pPropSpec,
  ULONG       *pulAccessFlags,
  PROPVARIANT *pPropVar
);
```

## Parameters

`pWiasContext`

Pointer to a WIA item context.

`cPropSpec`

Specifies the number of properties.

`pPropSpec`

Pointer to a PROPSPEC structure indicating the properties for which to set valid values and access flags.

`pulAccessFlags`

Pointer to an array that contains the access flags to be written.

`pPropVar`

Pointer to an array of PROPVARIANT structures that contains the valid values to be written.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## Remarks

Minidrivers should use the function <a href="https://msdn.microsoft.com/library/windows/hardware/ff549358">wiasSetItemPropAttribs</a> to initialize groups of simple properties.

The minidriver can set the WIA_PROP_CACHEABLE flag on a property that does not change over time. By setting this flag on a property, the minidriver indicates that the WIA service can cache the property value. See the Windows SDK documentation for a list of all property attributes.

The PROPSPEC and PROPVARIANT structures are defined in the Windows SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | wiamdef.h (include Wiamdef.h) |
| **Library** | Wiaservc.lib |
| **DLL** | Wiaservc.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549358">wiasSetItemPropAttribs</a>