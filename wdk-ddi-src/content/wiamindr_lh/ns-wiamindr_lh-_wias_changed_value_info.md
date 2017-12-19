---
UID: NS.WIAMINDR_LH._WIAS_CHANGED_VALUE_INFO
title: _WIAS_CHANGED_VALUE_INFO
author: windows-driver-content
description: The WIAS_CHANGED_VALUE_INFO structure is used to store the current and previous values of a property.
old-location: image\wias_changed_value_info.htm
old-project: Image
ms.assetid: bfef9d54-fcd5-436b-b3ec-8cd3b8f38360
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WIAS_CHANGED_VALUE_INFO, *PWIAS_CHANGED_VALUE_INFO, WIAS_CHANGED_VALUE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WIAS_CHANGED_VALUE_INFO
req.alt-loc: wiamindr_lh.h
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

# _WIAS_CHANGED_VALUE_INFO structure



## -description
The WIAS_CHANGED_VALUE_INFO structure is used to store the current and previous values of a property.



## -syntax

````
typedef struct _WIAS_CHANGED_VALUE_INFO {
  BOOL  bChanged;
  LONG  vt;
  union {
    LONG  lVal;
    FLOAT fltVal;
    BSTR  bstrVal;
    GUID  guidVal;
  } Old;
  union {
    LONG  lVal;
    FLOAT fltVal;
    BSTR  bstrVal;
    GUID  guidVal;
  } Current;
} WIAS_CHANGED_VALUE_INFO, *PWIAS_CHANGED_VALUE_INFO;
````


## -struct-fields

### -field bChanged

Is a Boolean that indicates whether a property has changed. That is, if the property's current value is different from its value before <a href="image.iwiaminidrv_drvvalidateitemproperties">IWiaMiniDrv::drvValidateItemProperties</a> was called. Upon return from one of the <b>wiasGetChangedValue</b><i>Xxx</i> functions, this member is <b>TRUE</b> if the property changed, and <b>FALSE</b> if the property did not change. 


### -field vt

Specifies the variant data type for the property. This member can be one of the following:

<dl>
<dd>
VT_UI1

</dd>
<dd>
VT_UI2

</dd>
<dd>
VT_UI4

</dd>
<dd>
VT_I2

</dd>
<dd>
VT_I4

</dd>
<dd>
VT_R4

</dd>
<dd>
VT_R8

</dd>
<dd>
VT_CLSID

</dd>
<dd>
VT_BSTR

</dd>
</dl>
See the PROPVARIANT structure in the Microsoft Windows SDK documentation for more information.


### -field Old


### -field Current


## -remarks
The <b>wiasGetChangedValue</b><i>Xxx</i> functions, use this structure to determine whether a property of a certain type has been changed by an application. These functions are used when the minidriver performs property validation, which occurs within the body of <a href="image.iwiaminidrv_drvvalidateitemproperties">IWiaMiniDrv::drvValidateItemProperties</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Me and in Windows XP and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wiamindr_lh.h (include Wiamindr.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="image.iwiaminidrv_drvvalidateitemproperties">IWiaMiniDrv::drvValidateItemProperties</a>
</dt>
<dt>
<a href="image.wiasgetchangedvaluefloat">wiasGetChangedValueFloat</a>
</dt>
<dt>
<a href="image.wiasgetchangedvalueguid">wiasGetChangedValueGuid</a>
</dt>
<dt>
<a href="image.wiasgetchangedvaluelong">wiasGetChangedValueLong</a>
</dt>
<dt>
<a href="image.wiasgetchangedvaluestr">wiasGetChangedValueStr</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20WIAS_CHANGED_VALUE_INFO structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

