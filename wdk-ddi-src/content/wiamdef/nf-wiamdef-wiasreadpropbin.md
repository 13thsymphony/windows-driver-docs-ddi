---
UID: NF.wiamdef.wiasReadPropBin
title: wiasReadPropBin function
author: windows-driver-content
description: The wiasReadPropBin function retrieves a binary-data property value from a WIA item.
old-location: image\wiasreadpropbin.htm
old-project: image
ms.assetid: f62b63e3-011b-43ef-b7f5-769aa00ff3ca
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: wiasReadPropBin
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
req.alt-api: wiasReadPropBin
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

# wiasReadPropBin function



## -description
The <b>wiasReadPropBin</b> function retrieves a binary-data property value from a WIA item.


## -syntax

````
HRESULT _stdcall wiasReadPropBin(
  _In_      BYTE   *pWiasContext,
            PROPID propid,
  _Out_     BYTE   **ppbVal,
  _Out_opt_ BYTE   **ppbValOld,
            BOOL   bMustExist
);
````


## -parameters

### -param pWiasContext [in]

Pointer to a WIA item context.

### -param propid 

Specifies the property identifier.

### -param ppbVal [out]

Pointer to a memory location that receives the address of a buffer allocated by this function. Upon return, the buffer contains the property's binary data.

### -param ppbValOld [out, optional]

Pointer to a memory location that receives the address of a buffer allocated by the minidriver. Upon return, the buffer contains the previous value of the property's binary data. If this information is not needed, this parameter can be set to <b>NULL</b>.

### -param bMustExist 

Indicates whether the property must exist. If set to <b>TRUE</b>, the property must exist; if set to <b>FALSE</b>, the property does not have to exist.

## -returns
On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## -remarks
This function allocates a buffer and stores its address in the <i>ppbVal</i> parameter. The minidriver must free the buffer by calling <b>CoTaskMemFree</b> (described in the Windows SDK documentation).

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
<a href="image.wiasreadpropfloat">wiasReadPropFloat</a>
</dt>
<dt>
<a href="image.wiasreadpropguid">wiasReadPropGuid</a>
</dt>
<dt>
<a href="image.wiasreadproplong">wiasReadPropLong</a>
</dt>
<dt>
<a href="image.wiasreadpropstr">wiasReadPropStr</a>
</dt>
<dt>
<a href="image.wiaswritepropbin">wiasWritePropBin</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasReadPropBin function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
