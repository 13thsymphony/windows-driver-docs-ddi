---
UID: NF:wiautil.wiauDbgHelper2
title: wiauDbgHelper2 function
author: windows-driver-content
description: The wiauDbgHelper2 function writes a message to a log file, or debugger, or both.
old-location: image\wiaudbghelper2.htm
old-project: image
ms.assetid: 577ce93a-5a90-4e85-afc6-3791f402c238
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiaudbghelper2, wiauDbgHelper2, wiauDbgHelper2 function [Imaging Devices], wiauFncs_6ccf146a-ec2e-4ca4-827a-dec2f8ea629d.xml, wiautil/wiauDbgHelper2
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wiautil.h
api_name:
-	wiauDbgHelper2
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# wiauDbgHelper2 function
The <b>wiauDbgHelper2</b> function writes a message to a log file, or debugger, or both.

## Syntax

```
void wiauDbgHelper2(
  LPCSTR prefix,
  LPCSTR fname,
  LPCSTR fmt,
  ...    
);
```

## Parameters

`prefix`

Pointer to a string containing a prefix (such as "ERROR " or "WARN ") associated with the message.

`fname`

Pointer to a string containing the name of the function or method into which the call to <b>wiauDbgHelper2</b> is inserted.

`fmt`

TBD

`Arg1`




## Return Value

None

## Remarks

The <b>wiauDbgHelper2</b> function enables those using it to write <b>printf</b>-style messages, with variable argument lists, to a log file or debugger. The following example demonstrates how this function might be used:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>wiauDbgHelper2("ERROR", "MyFunc", "Buffer size too small - %d bytes", BufSize);</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549627">wiauDbgDump</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549633">wiauDbgError</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549637">wiauDbgErrorHr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549649">wiauDbgHelper</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550161">wiauDbgTrace</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550163">wiauDbgWarning</a>