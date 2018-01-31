---
UID : NF:wiautil.wiauDbgError
title : wiauDbgError function
author : windows-driver-content
description : The wiauDbgError function logs an error message.
old-location : image\wiaudbgerror.htm
old-project : image
ms.assetid : 112d6f90-33b3-446b-943c-8995e6ec3378
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : wiauFncs_73184286-df53-4272-9fa8-aae1d1fb3dbc.xml, wiauDbgError, image.wiaudbgerror, wiauDbgError function [Imaging Devices], wiautil/wiauDbgError
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wiautil.h
req.include-header : Wiautil.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows XP and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SKIP_AMOUNT
req.product : Windows 10 or later.
---


# wiauDbgError function
The <b>wiauDbgError</b> function logs an error message.

## Syntax

````
inline void __stdcall wiauDbgError(
   LPCSTR   fname,
   LPCSTR   fmt, ...
);
````

## Parameters

`fname`

Pointer to a string containing the name of the function or method into which the call to <b>wiauDbgDump</b> is inserted.

`fmt`

TBD

``




## Return Value

None

## Remarks

The <b>wiauDbgError</b> typically is used to display an error message with no data, such as in the following example:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>wiauDbgError("Read", "Attempting to read past end of buffer");</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wiautil.h (include Wiautil.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\wiautil\nf-wiautil-wiaudbgwarning.md">wiauDbgWarning</a>

<a href="..\wiautil\nf-wiautil-wiaudbgdump.md">wiauDbgDump</a>

<a href="..\wiautil\nf-wiautil-wiaudbgerrorhr.md">wiauDbgErrorHr</a>

<a href="..\wiautil\nf-wiautil-wiaudbgtrace.md">wiauDbgTrace</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauDbgError function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>