---
UID: NF.wiamdef.WIAS_LTRACE
title: WIAS_LTRACE macro
author: windows-driver-content
description: The WIAS_LTRACE macro is obsolete for Windows Vista and later. It is recommended that the WIAS_TRACE macro be used instead.The WIAS_LTRACE macro writes a diagnostic WIA_TRACE message to the log file.
old-location: image\wias_ltrace.htm
old-project: image
ms.assetid: 513fd718-3d35-4a7b-be28-b002a8108e86
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: WIAS_LTRACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wiamdef.h
req.include-header: Wia.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me, Windows XP, and later versions of the operating system. Obsolete for Windows Vista and later. Use WIAS_TRACE instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WIAS_LTRACE
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
req.product: Windows 10 or later.
---

# WIAS_LTRACE macro



## -description
The WIAS_LTRACE macro is obsolete for Windows Vista and later. It is recommended that the <a href="image.wias_trace">WIAS_TRACE</a> macro be used instead.

The WIAS_LTRACE macro writes a diagnostic WIA_TRACE message to the log file.



## -syntax

````
WIAS_LTRACE( WIAS_LTRACE(
         IWiaLog   *pIWiaLog,
         INT       ResourceID,
         INT       DetailLevel,
   const CHAR      *format_string
);
````


## -parameters

### -param pIWiaLog 

Pointer to an <a href="image.iwialog_interface">IWiaLog Interface</a>.


### -param ResourceID 

Specifies the resource ID. This value should be set to WIALOG_NO_RESOURCE_ID.


### -param DetailLevel 

Specifies the diagnostic detail level of the message. This parameter can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
WIALOG_LEVEL1

</td>
<td>
Logs entry and exit points for all WIA methods and functions.

</td>
</tr>
<tr>
<td>
WIALOG_LEVEL2

</td>
<td>
Logs additional details for WIALOG_LEVEL1.

</td>
</tr>
<tr>
<td>
WIALOG_LEVEL3

</td>
<td>
Logs entry and exit points for all WIA methods and functions and additional vendor-supplied functions.

</td>
</tr>
<tr>
<td>
WIALOG_LEVEL4

</td>
<td>
Logs additional details for WIALOG_LEVEL3. 

</td>
</tr>
<tr>
<td>
WIALOG_LEVELXXX

</td>
<td>
User-defined log levels.

</td>
</tr>
</table>
 


### -param format_string 

Specifies a variable argument list, which starts with an ANSI format string describing the message and any format identifiers. The ellipsis (...) specifies a variable number of arguments that need to be output. The error text should be prefixed with the full name of the method or function and generate the message in the format of "class::method, error-text".


## -remarks
The following is an example of how the macro can be used:

The WIAS_LTRACE macro is not recommended for Windows Vista, because it does not record its output to the <i>Wiatrace.log </i>diagnostic Log file. It is recommended that the <a href="image.wias_trace">WIAS_TRACE</a> macro be used instead. 


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
Available in Windows Me, Windows XP, and later versions of the operating system. Obsolete for Windows Vista and later. Use WIAS_TRACE instead.

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
<a href="image.wias_lerror">WIAS_LERROR</a>
</dt>
<dt>
<a href="image.wias_lhresult">WIAS_LHRESULT</a>
</dt>
<dt>
<a href="image.wias_lwarning">WIAS_LWARNING</a>
</dt>
<dt>
<a href="image.wias_trace">WIAS_TRACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20WIAS_LTRACE macro%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

