---
UID: NF:wiautil.wiauDbgDump
title: wiauDbgDump function
author: windows-driver-content
description: The wiauDbgDump function logs a message containing one or more data values.
old-location: image\wiaudbgdump.htm
old-project: Image
ms.assetid: 5df074ff-572d-47f7-9c5c-4423b200cddc
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: wiautil/wiauDbgDump, wiauDbgDump function [Imaging Devices], image.wiaudbgdump, wiauDbgDump, wiauFncs_dbe56add-64ef-442d-9824-ed0b26aba9ac.xml
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wiautil.h
apiname:
-	wiauDbgDump
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# wiauDbgDump function
The <b>wiauDbgDump</b> function logs a message containing one or more data values.

## Syntax

````
inline void __stdcall wiauDbgDump(
   LPCSTR   fname,
   LPCSTR   fmt, ...
);
````

## Parameters

`fname`

Pointer to a string containing the name of the function or method into which the call to <b>wiauDbgDump</b> is inserted.

`fmt`

TBD

`Arg1`




## Return Value

None

## Remarks

The <b>wiauDbgDump</b> function typically is used to log a message along with one or more data values, as in the following example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>wiauDbgDump("SetBuffer", "Buffer size set to %d bytes.", size);</pre>
</td>
</tr>
</table></span></div>
This example, which would be placed in a function named <i>SetBuffer</i>, causes the function name and a string describing the size of a buffer to be logged.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\wiautil\nf-wiautil-wiaudbgtrace.md">wiauDbgTrace</a>



<a href="..\wiautil\nf-wiautil-wiaudbgerrorhr.md">wiauDbgErrorHr</a>



<a href="..\wiautil\nf-wiautil-wiaudbgwarning.md">wiauDbgWarning</a>



<a href="..\wiautil\nf-wiautil-wiaudbgerror.md">wiauDbgError</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20wiauDbgDump function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>