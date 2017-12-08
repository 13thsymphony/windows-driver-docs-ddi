---
UID: NF.wiamdef.wiasSetValidFlag
title: wiasSetValidFlag function
author: windows-driver-content
description: The wiasSetValidFlag function sets the valid values for a WIA_PROP_FLAG property.
old-location: image\wiassetvalidflag.htm
old-project: image
ms.assetid: 86690e6f-4b30-4de9-b380-8939ed983027
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: wiasSetValidFlag
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
req.alt-api: wiasSetValidFlag
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
req.product: Windows 10 or later.
---

# wiasSetValidFlag function



## -description
The <b>wiasSetValidFlag </b>function sets the valid values for a WIA_PROP_FLAG property.


## -syntax

````
HRESULT _stdcall wiasSetValidFlag(
  _In_ BYTE   *pWiasContext,
       PROPID propid,
       ULONG  ulNom,
       ULONG  ulValidBits
);
````


## -parameters

### -param pWiasContext [in]

Pointer to a WIA item context.

### -param propid 

Specifies the identifier of the property to be updated.

### -param ulNom 

Specifies the property's nominal value.

### -param ulValidBits 

Specifies the valid bits that can be used for the WIA_PROP_FLAG property.

## -returns
On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

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

## -see-also
<dl>
<dt>
<a href="image.wiassetvalidlistfloat">wiasSetValidListFloat</a>
</dt>
<dt>
<a href="image.wiassetvalidlistguid">wiasSetValidListGuid</a>
</dt>
<dt>
<a href="image.wiassetvalidlistlong">wiasSetValidListLong</a>
</dt>
<dt>
<a href="image.wiassetvalidliststr">wiasSetValidListStr</a>
</dt>
<dt>
<a href="image.wiassetvalidrangefloat">wiasSetValidRangeFloat</a>
</dt>
<dt>
<a href="image.wiassetvalidrangelong">wiasSetValidRangeLong</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasSetValidFlag function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
