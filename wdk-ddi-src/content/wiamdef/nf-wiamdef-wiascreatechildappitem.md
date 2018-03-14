---
UID: NF:wiamdef.wiasCreateChildAppItem
title: wiasCreateChildAppItem function
author: windows-driver-content
description: The wiasCreateChildAppItem function creates a new application item and inserts it as a child of the specified (parent) item. Note that this item will not have any properties in its property sets until the driver or application actually fills them in.
old-location: image\wiascreatechildappitem.htm
old-project: image
ms.assetid: 1dba59b0-5eac-4507-bd42-517a856aa864
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiascreatechildappitem, wiamdef/wiasCreateChildAppItem, wiasCreateChildAppItem, wiasCreateChildAppItem function [Imaging Devices], wiasFncs_63e9cbb1-6435-433b-a27f-36b66042be8a.xml
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
-	wiasCreateChildAppItem
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---


# wiasCreateChildAppItem function
The <b>wiasCreateChildAppItem</b> function creates a new application item and inserts it as a child of the specified (parent) item. Note that this item will not have any properties in its property sets until the driver or application actually fills them in.

## Syntax

````
HRESULT _stdcall wiasCreateChildAppItem(
  _In_  BYTE *pParentWiasContext,
        LONG lFlags,
  _In_  BSTR bstrItemName,
  _In_  BSTR bstrFullItemName,
  _Out_ BYTE **ppWiasChildContext
);
````

## Parameters

`pParentWiasContext`

Pointer to the item context to which the child will be added.

`lFlags`

Is reserved for system use.

`bstrItemName`

Specifies a string that contains the item name without path information.

`bstrFullItemName`

Specifies a string that contains the item name including path information.

`ppWiasChildContext`

Pointer to a memory location that receives the address of the newly created child item's context.


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

<a href="..\wiamdef\nf-wiamdef-wiascreatedrvitem.md">wiasCreateDrvItem</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasCreateChildAppItem function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>