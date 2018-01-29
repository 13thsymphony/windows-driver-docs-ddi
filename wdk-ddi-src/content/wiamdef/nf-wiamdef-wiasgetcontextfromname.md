---
UID : NF:wiamdef.wiasGetContextFromName
title : wiasGetContextFromName function
author : windows-driver-content
description : The wiasGetContextFromName function retrieves the item context for an item name.
old-location : image\wiasgetcontextfromname.htm
old-project : image
ms.assetid : d15bf48e-132d-4f89-8f19-64f57deed500
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : wiamdef/wiasGetContextFromName, wiasGetContextFromName function [Imaging Devices], image.wiasgetcontextfromname, wiasFncs_ba1c88a2-aadc-4c2f-bb5f-88433d1e1760.xml, wiasGetContextFromName
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
req.typenames : DEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2
req.product : Windows 10 or later.
---


# wiasGetContextFromName function
The <b>wiasGetContextFromName</b> function retrieves the item context for an item name.

## Syntax

````
HRESULT _stdcall wiasGetContextFromName(
  _In_  BYTE *pWiasContext,
        LONG lFlags,
  _In_  BSTR bstrName,
  _Out_ BYTE **ppWiasContext
);
````

## Parameters

`pWiasContext`

Pointer to a WIA item context.

`lFlags`

Reserved for system use and should be set to 0.

`bstrName`

Specifies the name of the context that is being searched for.

`ppWiasContext`

Pointer to a memory location that receives the address of the WIA item context.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## Remarks

This function searches for item contexts whose WIA_IPA_FULL_ITEM_NAME property matches <i>bstrName</i>. Note that this property is different from WIA_IPA_ITEM_NAME, which does not contain path information.

This function should be used by minidrivers when they need to move from one application item context to another, given the item's name. The names of the application items come from their corresponding driver items, which the minidriver creates and names.

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

## See Also

<a href="..\wiamdef\nf-wiamdef-wiasgetrootitem.md">wiasGetRootItem</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasGetContextFromName function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>