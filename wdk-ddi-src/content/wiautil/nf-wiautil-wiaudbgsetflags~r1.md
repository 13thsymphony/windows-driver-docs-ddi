---
UID: NF.wiautil.wiauDbgSetFlags~r1
title: wiauDbgSetFlags macro
author: windows-driver-content
description: The wiauDbgSetFlags function sets debugging flags.
old-location: image\wiaudbgsetflags.htm
old-project: Image
ms.assetid: e3b944ef-daa5-412c-ac11-7b08d2b9333b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: wiauDbgSetFlags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: wiauDbgSetFlags
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

# wiauDbgSetFlags macro



## -description
The <b>wiauDbgSetFlags</b> function sets debugging flags.



## -syntax

````
inline DWORD __stdcall wiauDbgSetFlags(
   DWORD flags
);
````


## -parameters

### -param flags 

Is a set of flags that control message logging. This parameter can be set to a combination of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WIAUDBG_BREAK_ON_ERRORS

</td>
<td>
Call <b>DebugBreak</b> (described in the Microsoft Windows SDK documentation) when an error occurs.

</td>
</tr>
<tr>
<td>
WIAUDBG_DONT_LOG

</td>
<td>
Do not log to either log file or debugger.

</td>
</tr>
<tr>
<td>
WIAUDBG_DONT_LOG_TO_DEBUGGER

</td>
<td>
Do not log to debugger.

</td>
</tr>
<tr>
<td>
WIAUDBG_DONT_LOG_TO_FILE

</td>
<td>
Do not log to log file.

</td>
</tr>
<tr>
<td>
WIAUDBG_DUMP

</td>
<td>
Log data.

</td>
</tr>
<tr>
<td>
WIAUDBG_ERRORS

</td>
<td>
Log error messages.

</td>
</tr>
<tr>
<td>
WIAUDBG_FNS

</td>
<td>
Log function entries and exits.

</td>
</tr>
<tr>
<td>
WIAUDBG_PRINT_INFO

</td>
<td>
Log thread, file, and line number.

</td>
</tr>
<tr>
<td>
WIAUDBG_PRINT_TIME

</td>
<td>
Log current time.

</td>
</tr>
<tr>
<td>
WIAUDBG_TRACES

</td>
<td>
Log trace messages.

</td>
</tr>
<tr>
<td>
WIAUDBG_WARNINGS

</td>
<td>
Log warning messages.

</td>
</tr>
</table>
 


## -remarks


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

## -see-also
<dl>
<dt>
<a href="image.wiaudbgflags">wiauDbgFlags</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20wiauDbgSetFlags function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

