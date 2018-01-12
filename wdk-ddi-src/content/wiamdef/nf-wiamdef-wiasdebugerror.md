---
UID: NF:wiamdef.wiasDebugError
title: wiasDebugError function
author: windows-driver-content
description: This function prints a debug error string in the Device Manager debug console. The output color is always red.
old-location: image\wiasdebugerror.htm
old-project: image
ms.assetid: fcddc83d-5fb1-43ad-9abd-8d5e2549b580
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: wiasDebugError
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
req.alt-api: wiasDebugError
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
req.typenames: *LPDEVICEDIALOGDATA2, DEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---

# wiasDebugError function



## -description
This function prints a debug error string in the Device Manager debug console. The output color is always red.



## -syntax

````
VOID __cdecl wiasDebugError(
   HINSTANCE   hInstance,
   LPCSTR      pszFormat, ...
);
````


## -parameters

### -param hInstance 

Is the module handle of calling module.


### -param pszFormat, ... 

Specifies a variable argument list, which starts with an ANSI format string containing the message and any format specifiers. The ellipsis (...) specifies a variable number of arguments that are to be output.


## -returns
On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).


## -remarks
The wiasDebugError function is not recommended for Windows XP and later. For Windows XP use the <a href="..\wiamdef\nf-wiamdef-wias_lerror.md">WIAS_LERROR</a> macro instead. For Windows Vista use the <a href="..\wiamdef\nf-wiamdef-wias_error.md">WIAS_ERROR</a> macro instead.


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
<a href="..\wiamdef\nf-wiamdef-wias_lerror.md">WIAS_LERROR</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wias_error.md">WIAS_ERROR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasDebugError function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

