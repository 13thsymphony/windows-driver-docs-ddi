---
UID: NF.wiamdef.wiasReadMultiple
title: wiasReadMultiple function
author: windows-driver-content
description: The wiasReadMultiple function retrieves multiple property values from a WIA item.
old-location: image\wiasreadmultiple.htm
old-project: image
ms.assetid: 814642f7-24df-4d64-bc2b-d76d84b2a6d3
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: wiasReadMultiple
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
req.alt-api: wiasReadMultiple
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

# wiasReadMultiple function



## -description
The <b>wiasReadMultiple </b>function retrieves multiple property values from a WIA item.


## -syntax

````
HRESULT _stdcall wiasReadMultiple(
  _In_            BYTE        *pWiasContext,
                  ULONG       ulCount,
  _In_      const PROPSPEC    *ps,
  _Out_           PROPVARIANT *pv,
  _Out_opt_       PROPVARIANT *pvOld
);
````


## -parameters

### -param pWiasContext [in]

Pointer to a WIA item context.

### -param ulCount 

Specifies the number of properties to read.

### -param ps [in]

Pointer to the first element of an array of PROPSPEC structures, containing the properties to read.

### -param pv [out]

Pointer to the first element of an array of PROPVARIANT structures. Upon return, these structures contain new values for the properties.

### -param pvOld [out, optional]

Pointer to the first element of an array of PROPVARIANT structures previously allocated by the minidriver. Upon return, the array contains the previous values of the property data. If this information is not needed, this parameter can be set to <b>NULL</b>.

## -returns
On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## -remarks
This function reads multiple properties from a WIA item. When the call succeeds, the minidriver must call <b>PropVariantClear</b> on each element in the array specified by the <i>pv</i> parameter. See <b>IPropertyStorage::ReadMultiple</b> for more information.

PROPSPEC, PROPVARIANT, <b>PropVariantClear</b>, and <b>IPropertyStorage::ReadMultiple</b> are described in the Windows SDK documentation.

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
<a href="image.wiaswritemultiple">wiasWriteMultiple</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasReadMultiple function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
