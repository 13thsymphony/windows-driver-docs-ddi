---
UID: NF:wiamdef.wiasSetValidFlag
title: wiasSetValidFlag function
author: windows-driver-content
description: The wiasSetValidFlag function sets the valid values for a WIA_PROP_FLAG property.
old-location: image\wiassetvalidflag.htm
old-project: image
ms.assetid: 86690e6f-4b30-4de9-b380-8939ed983027
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiassetvalidflag, wiamdef/wiasSetValidFlag, wiasFncs_4c84b6c9-20fe-4894-b3fc-f7d84742827a.xml, wiasSetValidFlag, wiasSetValidFlag function [Imaging Devices]
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
-	wiasSetValidFlag
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---


# wiasSetValidFlag function
The <b>wiasSetValidFlag </b>function sets the valid values for a WIA_PROP_FLAG property.

## Syntax

````
HRESULT _stdcall wiasSetValidFlag(
  _In_ BYTE   *pWiasContext,
       PROPID propid,
       ULONG  ulNom,
       ULONG  ulValidBits
);
````

## Parameters

`pWiasContext`

Pointer to a WIA item context.

`propid`

Specifies the identifier of the property to be updated.

`ulNom`

Specifies the property's nominal value.

`ulValidBits`

Specifies the valid bits that can be used for the WIA_PROP_FLAG property.


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

<a href="..\wiamdef\nf-wiamdef-wiassetvalidrangefloat.md">wiasSetValidRangeFloat</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidlistfloat.md">wiasSetValidListFloat</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidliststr.md">wiasSetValidListStr</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidrangelong.md">wiasSetValidRangeLong</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidlistlong.md">wiasSetValidListLong</a>



<a href="..\wiamdef\nf-wiamdef-wiassetvalidlistguid.md">wiasSetValidListGuid</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasSetValidFlag function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>