---
UID: NF:wiamdef.wiasGetChildrenContexts
title: wiasGetChildrenContexts function
author: windows-driver-content
description: The wiasGetChildrenContexts function retrieves an array of item contexts belonging to the current item's children.
old-location: image\wiasgetchildrencontexts.htm
old-project: image
ms.assetid: a69216f4-1272-488f-8d06-8dc3b6a88452
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: wiasGetChildrenContexts
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
req.alt-api: wiasGetChildrenContexts
req.alt-loc: Wiaservc.dll
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
req.typenames: *LPDEVICEDIALOGDATA2, DEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---

# wiasGetChildrenContexts function



## -description
The <b>wiasGetChildrenContexts</b> function retrieves an array of item contexts belonging to the current item's children.



## -syntax

````
HRESULT _stdcall wiasGetChildrenContexts(
  _In_  BYTE  *pParentContext,
  _Out_ ULONG *pulNumChildren,
  _Out_ BYTE  ***pppChildren
);
````


## -parameters

### -param pParentContext [in]

Pointer to the parent item.


### -param pulNumChildren [out]

Pointer to a memory location that receives the number of children contexts.


### -param pppChildren [out]

Pointer to a memory location that points to an array whose elements are addresses of <b>IWiaItem</b> objects (described in the Microsoft Windows SDK documentation). Each <b>IWiaItem</b> object represents one child context.


## -returns
On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Windows SDK documentation).


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wiamdef.h (include Wiamdef.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wiaservc.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Wiaservc.dll</dt>
</dl>
</td>
</tr>
</table>