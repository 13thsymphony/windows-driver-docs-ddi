---
UID: NF:wiautil.wiauDbgErrorHr
title: wiauDbgErrorHr function
author: windows-driver-content
description: The wiauDbgErrorHr function logs a message containing an HRESULT and its error message string.
old-location: image\wiaudbgerrorhr.htm
old-project: image
ms.assetid: 18d248d9-d447-4d3e-9eaa-f6befb4bef58
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiaudbgerrorhr, wiauDbgErrorHr, wiauDbgErrorHr function [Imaging Devices], wiauFncs_1400188e-53d1-481c-a470-8a2247b7f34f.xml, wiautil/wiauDbgErrorHr
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
-	wiauDbgErrorHr
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# wiauDbgErrorHr function
The <b>wiauDbgErrorHr</b> function logs a message containing an HRESULT and its error message string.

## Syntax

```
void wiauDbgErrorHr(
  HRESULT hr,
  LPCSTR  fname,
  LPCSTR  fmt,
  ...     
);
```

## Parameters

`hr`

Specifies the HRESULT that is to be logged.

`fname`

Pointer to a string containing the name of the function or method into which the call to <b>wiauDbgDump</b> is inserted.

`fmt`

TBD

`Arg1`




## Return Value

None

## Remarks

The <b>wiauDbgErrorHr</b> function typically logs two lines to the log file, or debugger, or both. The first line contains the text of the <i>fmt</i> parameter, including data, if provided. The second line contains the HRESULT and the message string associated with that HRESULT. The following example shows how this function might be called:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>wiauDbgErrorHr(hr, "AllocateBuffer", "Buffer size is %d bytes", size);</pre>
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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550161">wiauDbgTrace</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550163">wiauDbgWarning</a>