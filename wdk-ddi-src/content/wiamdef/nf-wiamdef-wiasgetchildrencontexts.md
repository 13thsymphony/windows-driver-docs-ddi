---
UID : NF:wiamdef.wiasGetChildrenContexts
title : wiasGetChildrenContexts function
author : windows-driver-content
description : The wiasGetChildrenContexts function retrieves an array of item contexts belonging to the current item's children.
old-location : image\wiasgetchildrencontexts.htm
old-project : image
ms.assetid : a69216f4-1272-488f-8d06-8dc3b6a88452
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : wiasGetChildrenContexts function [Imaging Devices], wiamdef/wiasGetChildrenContexts, wiasGetChildrenContexts, image.wiasgetchildrencontexts, wiasFncs_fff487b8-2797-4df4-ae22-f25c08f21dfc.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wiamdef.h
req.include-header : Wiamdef.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wiaservc.lib
req.dll : Wiaservc.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PDEVICEDIALOGDATA2, DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2"
req.product : Windows 10 or later.
---


# wiasGetChildrenContexts function
The <b>wiasGetChildrenContexts</b> function retrieves an array of item contexts belonging to the current item's children.

## Syntax

````
HRESULT _stdcall wiasGetChildrenContexts(
  _In_  BYTE  *pParentContext,
  _Out_ ULONG *pulNumChildren,
  _Out_ BYTE  ***pppChildren
);
````

## Parameters

`pParentContext`

Pointer to the parent item.

`pulNumChildren`

Pointer to a memory location that receives the number of children contexts.

`pppChildren`

Pointer to a memory location that points to an array whose elements are addresses of <b>IWiaItem</b> objects (described in the Microsoft Windows SDK documentation). Each <b>IWiaItem</b> object represents one child context.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Windows SDK documentation).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wiamdef.h (include Wiamdef.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |