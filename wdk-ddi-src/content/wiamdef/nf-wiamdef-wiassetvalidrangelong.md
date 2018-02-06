---
UID: NF:wiamdef.wiasSetValidRangeLong
title: wiasSetValidRangeLong function
author: windows-driver-content
description: The wiasSetValidRangeLong function specifies the range of valid values for a WIA_PROP_RANGE property of type VT_I4.
old-location: image\wiassetvalidrangelong.htm
old-project: image
ms.assetid: ff4badb5-ab27-4deb-864a-51165290bca4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiasSetValidRangeLong function [Imaging Devices], image.wiassetvalidrangelong, wiasSetValidRangeLong, wiamdef/wiasSetValidRangeLong, wiasFncs_3ee53b59-4ef4-4c35-8544-1ac7a8729212.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Wiaservc.dll
apiname:
-	wiasSetValidRangeLong
product: Windows
targetos: Windows
req.typenames: "*LPDEVICEDIALOGDATA2, DEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2"
req.product: Windows 10 or later.
---


# wiasSetValidRangeLong function
The <b>wiasSetValidRangeLong </b>function specifies the range of valid values for a WIA_PROP_RANGE property of type VT_I4.

## Syntax

````
HRESULT _stdcall wiasSetValidRangeLong(
  _In_ BYTE   *pWiasContext,
       PROPID propid,
       LONG   lMin,
       LONG   lNom,
       LONG   lMax,
       LONG   lStep
);
````

## Parameters

`pWiasContext`

Pointer to a WIA item context.

`propid`

Specifies the identifier of the property to be updated.

`lMin`

Specifies the minimum value of the valid range.

`lNom`

Specifies the property's nominal value.

`lMax`

Specifies the maximum value of the valid range.

`lStep`

Specifies the increment between each valid value in the range.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems. Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | wiamdef.h (include Wiamdef.h) |
| **Library** | Wiaservc.lib |
| **DLL** | Wiaservc.dll |

## See Also

<a href="..\wiamdef\nf-wiamdef-wiassetvalidlistguid.md">wiasSetValidListGuid</a>

<a href="..\wiamdef\nf-wiamdef-wiassetvalidlistfloat.md">wiasSetValidListFloat</a>

<a href="..\wiamdef\nf-wiamdef-wiassetvalidflag.md">wiasSetValidFlag</a>

<a href="..\wiamdef\nf-wiamdef-wiassetvalidlistlong.md">wiasSetValidListLong</a>

<a href="..\wiamdef\nf-wiamdef-wiassetvalidliststr.md">wiasSetValidListStr</a>

<a href="..\wiamdef\nf-wiamdef-wiassetvalidrangefloat.md">wiasSetValidRangeFloat</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasSetValidRangeLong function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>