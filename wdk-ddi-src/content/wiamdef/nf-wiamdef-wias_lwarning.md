---
UID: NF:wiamdef.WIAS_LWARNING
title: WIAS_LWARNING macro
author: windows-driver-content
description: The WIAS_LWARNING macro is obsolete for Windows Vista and later.The WIAS_LWARNING macro writes a diagnostic WIA_WARNING message to the log file.
old-location: image\wias_lwarning.htm
old-project: image
ms.assetid: 2959c470-1da7-4396-a591-7a356379f9de
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: WIAS_LWARNING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wiamdef.h
req.include-header: Wia.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me, Windows XP, and later. Obsolete for Windows Vista and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WIAS_LWARNING
req.alt-loc: wiamdef.h
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
req.typenames: *LPDEVICEDIALOGDATA2, DEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---

# WIAS_LWARNING macro



## -description
The WIAS_LWARNING macro is obsolete for Windows Vista and later.

The WIAS_LWARNING macro writes a diagnostic WIA_WARNING message to the log file.



## -syntax

````
WIAS_LERROR( WIAS_LWARNING(
         IWiaLog   *pIWiaLog,
         LONG      lResId,
   const CHAR      *format_string, ...
);
````


## -parameters

### -param pIWiaLog 

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff543935">IWiaLog Interface</a>.


### -param lResId 

Specifies the resource ID. This value should be set to WIALOG_NO_RESOURCE_ID.


### -param format_string, ... 

Specifies a variable argument list, which starts with an ANSI format string that describes the message and any format identifiers. The ellipsis (...) specifies a variable number of arguments that need to be output. The error text should be prefixed with the full name of the method or function and generate the message in the format of "class::method, error-text".


## -remarks
The following is an example of how the macro can be used:

Please note that it does not write to the new log file used in Windows Vista and later.


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
Available in Windows Me, Windows XP, and later. Obsolete for Windows Vista and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wiamdef.h (include Wia.h)</dt>
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
<a href="..\wiamdef\nf-wiamdef-wias_lhresult.md">WIAS_LHRESULT</a>
</dt>
<dt>
<a href="..\wiamdef\nf-wiamdef-wias_ltrace.md">WIAS_LTRACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20WIAS_LWARNING macro%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

