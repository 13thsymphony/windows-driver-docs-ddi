---
UID: NF.wiautil.wiauSetImageItemSize~r1
title: wiauSetImageItemSize function
author: windows-driver-content
description: The wiauSetImageItemSize function calculates the size and width, in bytes, for an image, based on the current WIA_IPA_FORMAT setting (described in the Microsoft Windows SDK documentation), and writes the new values to the appropriate properties.
old-location: image\wiausetimageitemsize.htm
old-project: image
ms.assetid: 5bf56435-df81-4555-91ca-5419883bb1e8
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: wiauSetImageItemSize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: wiauSetImageItemSize
req.alt-loc: wiautil.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# wiauSetImageItemSize function



## -description
The <b>wiauSetImageItemSize</b> function calculates the size and width, in bytes, for an image, based on the current WIA_IPA_FORMAT setting (described in the Microsoft Windows SDK documentation), and writes the new values to the appropriate properties.



## -syntax

````
HRESULT _stdcall wiauSetImageItemSize(
  _In_     BYTE          *pWiasContext,
           LONG          lWidth,
           LONG          lHeight,
           LONG          lDepth,
           LONG          lSize,
  _In_opt_ PWSTR pwszExt pwszExt
);
````


## -parameters

### -param pWiasContext [in]

Pointer to a WIA item context.


### -param lWidth 

Specifies the width of the image, in pixels.


### -param lHeight 

Specifies the height of the image, in pixels.


### -param lDepth 

Specifies the depth of the image, in bits.


### -param lSize 

Specifies the size of the image as stored on the device.


### -param pwszExt [in, optional]

<i>Optional</i>. Pointer to a memory location containing a three-character file name extension for the item's native format. If this parameter is <b>NULL</b>, the item's extension property, WIA_IPA_FILENAME_EXTENSION (described in the Windows SDK documentation), is not updated.


## -returns
On success, the function returns S_OK. If the function fails, it returns a standard COM error.


## -remarks
If the format is not BMP, this function assumes that the value passed in the <i>lSize</i> parameter is correct for the current format.


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
Available in Windows XP and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wiautil.h (include Wiautil.h)</dt>
</dl>
</td>
</tr>
</table>