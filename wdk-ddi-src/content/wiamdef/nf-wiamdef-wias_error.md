---
UID: NF.wiamdef.WIAS_ERROR
title: WIAS_ERROR macro
author: windows-driver-content
description: The WIAS_ERROR macro writes a diagnostic message to the Wiatrace.log file.
old-location: image\wias_error.htm
old-project: Image
ms.assetid: e439f130-1b99-4f46-ace5-3456c09a5f67
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: WIAS_ERROR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WIAS_ERROR
req.alt-loc: Wiamdef.h
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

# WIAS_ERROR macro



## -description
The WIAS_ERROR macro writes a diagnostic message to the <i>Wiatrace.log</i> file.



## -syntax

````
WIAS_ERROR( WIAS_ERROR(
         HInst  HInst,
   const CHAR   *format_string, ...
);
````


## -parameters

### -param HInst 

Handle to the DLL (driver).


### -param format_string, ... 

Specifies a variable argument list, which starts with an ANSI format string that describes the message and any format identifiers. The ellipsis (...) specifies a variable number of arguments that need to be output. The error text should be prefixed with the full name of the method or function and generate the message in the format of "class::method, error-text".


## -remarks
This macro is the recommended way to implement error logging on Windows Vista, because unlike <a href="image.wias_ltrace">WIAS_LERROR</a>, WIA_ERROR allows error messages to be written to the log file (<i>Wiatrace.log</i>). The <i>Wiatrace.log</i> file is only available in Windows Vista and later versions of the operating system. The utility used to view the contents of this log file is WiaTrcVw.exe.

To enable tracing in free builds, drivers must define the WIA_DEBUG macro by adding <code>#define WIA_DEBUG</code> before including any of the WIA headers. Tracing is enabled by default in checked and debug builds of the operating system.

The following is an example of how the macro can be used:

This code snippet was taken from <i>Wiadriver.cpp</i>, which is included with the WDK.


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
Available in Windows Vista and later versions of the operating system.

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
</table>

## -see-also
<dl>
<dt>
<a href="image.wias_assert">WIAS_ASSERT</a>
</dt>
<dt>
<a href="image.wias_hresult">WIAS_HRESULT</a>
</dt>
<dt>
<a href="image.wias_trace">WIAS_TRACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20WIAS_ERROR macro%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

