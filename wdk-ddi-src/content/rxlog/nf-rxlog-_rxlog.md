---
UID: NF.rxlog._RxLog
title: _RxLog function
author: windows-driver-content
description: _RxLog takes a format string and variable number of parameters and formats an output string for recording as an I/O error log entry if logging is enabled.
old-location: ifsk\_rxlog.htm
old-project: ifsk
ms.assetid: 00f6c2d9-7521-46c8-b37e-2be304d8a045
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _RxLog
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxlog.h
req.include-header: Rxlog.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: _RxLog
req.alt-loc: rxlog.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# _RxLog function



## -description
<b>_RxLog</b> takes a format string and variable number of parameters and formats an output string for recording as an I/O error log entry if logging is enabled. 



## -syntax

````
VOID _RxLog(
   char *Format
);
````


## -parameters

### -param Format 

The variable argument list that contains a format string and a variable number of parameters.


## -returns
None


## -remarks
It is recommended that the <b>RxLog</b> macro be used instead of calling the <b>_RxLog</b> routine directly.

If logging is enabled, <b>_RxLog</b> will output a string for recording as an I/O error log entry based on the format string and number of variables passed.

The <b>_RxLog</b> routine supports the following format string descriptors:

%lN, %wN, %lS, %wS, %ld, %wd--a number

%x--a hexadecimal number

%c--a character

%s--an ASCII string

%Z--a Unicode string that contains ASCII characters

The <b>_RxLog</b> routine is limited to an output string of, at most, 48 lines, so the <i>Format</i> string cannot contain more than 48 '\n' characters. 

It is recommended that the <b>RxLog</b> macro be used to call this routine. On checked builds, the <b>RxLog</b> macro will call the <b>_RxLog</b> routine. On retail builds, the <b>RxLog</b> macro is defined to nothing.


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
Header

</th>
<td width="70%">
<dl>
<dt>Rxlog.h (include Rxlog.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.rxlogeventdirect">RxLogEventDirect</a>
</dt>
<dt>
<a href="ifsk.rxlogeventwithannotation">RxLogEventWithAnnotation</a>
</dt>
<dt>
<a href="ifsk.rxlogeventwithbufferdirect">RxLogEventWithBufferDirect</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20_RxLog function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

