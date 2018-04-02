---
UID: NF:wiautil.wiauDbgDump
title: wiauDbgDump function
author: windows-driver-content
description: The wiauDbgDump function logs a message containing one or more data values.
old-location: image\wiaudbgdump.htm
old-project: image
ms.assetid: 5df074ff-572d-47f7-9c5c-4423b200cddc
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiaudbgdump, wiauDbgDump, wiauDbgDump function [Imaging Devices], wiauFncs_dbe56add-64ef-442d-9824-ed0b26aba9ac.xml, wiautil/wiauDbgDump
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
-	wiauDbgDump
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# wiauDbgDump function
The <b>wiauDbgDump</b> function logs a message containing one or more data values.

## Syntax

```
void wiauDbgDump(
  LPCSTR fname,
  LPCSTR fmt,
  ...    
);
```

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

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549633">wiauDbgError</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549637">wiauDbgErrorHr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550161">wiauDbgTrace</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550163">wiauDbgWarning</a>