---
UID : NF:wiamdef.wiasReadPropStr
title : wiasReadPropStr function
author : windows-driver-content
description : The wiasReadPropStr function retrieves a string property value from a WIA item.
old-location : image\wiasreadpropstr.htm
old-project : image
ms.assetid : b072b4ec-790f-454b-b94a-bfe44674f600
ms.author : windowsdriverdev
ms.date : 1/17/2018
ms.keywords : wiasReadPropStr
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
req.alt-api : wiasReadPropStr
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


# wiasReadPropStr function
The <b>wiasReadPropStr</b> function retrieves a string property value from a WIA item.

## Syntax

````
HRESULT _stdcall wiasReadPropStr(
  _In_      BYTE   *pWiasContext,
            PROPID propid,
  _Out_     BSTR   *pbstr,
  _Out_opt_ BSTR   *pbstrOld,
            BOOL   bMustExist
);
````

## Parameters

`pWiasContext`

Pointer to a WIA item context.

`propid`

Specifies the property identifier.

`pbstr`

Pointer to a memory location that receives the first byte of the property's string value.

`pbstrOld`

Pointer to a memory location that receives the first byte of the property's previous value. If this information is not needed, set this parameter to <b>NULL</b>.

`bMustExist`

Indicates whether the property must exist. If set to <b>TRUE</b>, the property must exist; if set to <b>FALSE</b>, the property does not have to exist.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## Remarks

When the minidriver has completed using the string it received from this function, it must deallocate the memory used for the string.

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
<a href="..\wiamdef\nf-wiamdef-wiasreadpropbin.md">wiasReadPropBin</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiasreadpropfloat.md">wiasReadPropFloat</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiasreadpropguid.md">wiasReadPropGuid</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiasreadproplong.md">wiasReadPropLong</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wiaswritepropstr.md">wiasWritePropStr</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasReadPropStr function%20 RELEASE:%20(1/17/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>