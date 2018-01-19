---
UID : NF:wiamdef.wiasIsPropChanged
title : wiasIsPropChanged function
author : windows-driver-content
description : The wiasIsPropChanged function tests whether a specified property has been changed by an application.
old-location : image\wiasispropchanged.htm
old-project : image
ms.assetid : 4b8f140c-ca4f-48fd-bee4-35d5a7beea52
ms.author : windowsdriverdev
ms.date : 1/17/2018
ms.keywords : wiasIsPropChanged
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
req.alt-api : wiasIsPropChanged
req.alt-loc : Wiaservc.dll
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
req.typenames : "*PDEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, DEVICEDIALOGDATA2"
req.product : Windows 10 or later.
---


# wiasIsPropChanged function
The <b>wiasIsPropChanged </b>function tests whether a specified property has been changed by an application.

## Syntax

````
HRESULT _stdcall wiasIsPropChanged(
        PROPID               props,
  _In_  WIA_PROPERTY_CONTEXT *pContext,
  _Out_ BOOL                 *pbChanged
);
````

## Parameters

`propid`



`pContext`

Pointer to a <a href="..\wiamindr_lh\ns-wiamindr_lh-_wia_property_context.md">WIA_PROPERTY_CONTEXT</a> structure that contains the current property context.

`pbChanged`

Pointer to a memory location that receives a BOOL value. The BOOL value is <b>TRUE</b> if the property changed, and <b>FALSE</b> if the property did not change.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## Remarks

This function determines whether a property is being changed by looking at the <b>bChanged</b> member value in the property's <a href="..\wiamindr_lh\ns-wiamindr_lh-_wia_property_context.md">WIA_PROPERTY_CONTEXT</a> structure. Minidrivers typically use this function to check when an independent property has been changed so that its dependents can be updated.

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

<dl>
<dt>
<a href="..\wiamindr_lh\ns-wiamindr_lh-_wia_property_context.md">WIA_PROPERTY_CONTEXT</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiasgetchangedvaluefloat.md">wiasGetChangedValueFloat</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiasgetchangedvalueguid.md">wiasGetChangedValueGuid</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiasgetchangedvaluelong.md">wiasGetChangedValueLong</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiasgetchangedvaluestr.md">wiasGetChangedValueStr</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasIsPropChanged function%20 RELEASE:%20(1/17/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>