---
UID: NF.wiamdef.wiasSetItemPropAttribs
title: wiasSetItemPropAttribs function
author: windows-driver-content
description: The wiasSetItemPropAttribs function sets the access flags and valid values for an item's set of properties.
old-location: image\wiassetitempropattribs.htm
old-project: image
ms.assetid: 354d09c3-8db4-4af9-b077-8e3bcda7a6f2
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: wiasSetItemPropAttribs
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
req.alt-api: wiasSetItemPropAttribs
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

# wiasSetItemPropAttribs function



## -description
The <b>wiasSetItemPropAttribs </b>function sets the access flags and valid values for an item's set of properties.


## -syntax

````
HRESULT _stdcall wiasSetItemPropAttribs(
  _In_ BYTE               *pWiasContext,
       LONG               cPropSpec,
  _In_ PROPSPEC           *pPropSpec,
  _In_ PWIA_PROPERTY_INFO pwpi
);
````


## -parameters

### -param pWiasContext [in]

Pointer to a WIA item context.

### -param cPropSpec 

Specifies the number of properties.

### -param pPropSpec [in]

Pointer to the first element of an array of PROPSPEC structures (defined in the Microsoft Windows SDK documentation) indicating the properties for which to set valid values and access flags.

### -param pwpi [in]

Pointer to the first element of an array of <a href="image.wia_property_info">WIA_PROPERTY_INFO</a> structures that contain the property values to be written.

## -returns
On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Windows SDK documentation).

## -remarks
Minidrivers should use this function to initialize groups of simple properties. The groups of properties can be bitsets, ranges of values, or lists of values. The supported simple types, grouped by attribute are as follows. 

WIA_PROP_FLAG

VT_UI1, VT_UI2, VT_UI4, VT_UI8, VT_I1, VT_I2, VT_I4, VT_I8

WIA_PROP_RANGE

VT_UI1, VT_UI2, VT_UI4, VT_UI8, VT_I1, VT_I2, VT_I4, ,VT_I8, VT_R4, VT_R8

WIA_PROP_LIST

VT_UI1, VT_UI2, VT_UI4, VT_UI8, VT_I1, VT_I2, VT_I4, ,VT_I8, VT_R4, VT_R8, VT_BSTR

Minidrivers should initialize complex properties using the <a href="image.wiassetpropertyattributes">wiasSetPropertyAttributes</a> function.

The minidriver can set the WIA_PROP_CACHEABLE flag on a property that does not change over time. By setting this flag on a property, the minidriver indicates that the WIA service can cache the property value. See the Windows SDK documentation for a list of all property attributes.

It is important to remember that <b>wiasSetItemPropAttribs</b> returns an HRESULT, not a BOOLEAN. For example, if <b>wiasSetItemPropAttribs</b> returns 0, this value must be interpreted as S_OK rather than <b>FALSE</b>, and indicates that everything worked as expected. If <b>wiasSetItemPropAttribs</b> returns the HRESULT S_FALSE, this indicates that one of the properties you are trying to set probably does not exist in the property stream.

To get a wiadebug log of this error, open the registry and turn on WIA logging for Warnings and Errors. The registry key for this is: <b>HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\StillImage\Debug\wiaservc.dll</b>

Set the value of "DebugFlags." to 0x00000003 

Reboot the system and repeat the steps necessary to produce this error. There will now be a file named "wiadebug.log" in %windir% directory.

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
<a href="image.wiassetpropertyattributes">wiasSetPropertyAttributes</a>
</dt>
<dt>
<a href="image.wiassetitempropnames">wiasSetItemPropNames</a>
</dt>
<dt>
<a href="image.wia_property_info">WIA_PROPERTY_INFO</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasSetItemPropAttribs function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
