---
UID: NF:wiautil.wiauDbgWarning
title: wiauDbgWarning function
author: windows-driver-content
description: The wiauDbgWarning function logs a warning message.
old-location: image\wiaudbgwarning.htm
old-project: image
ms.assetid: f10f1c28-0bfd-44c5-a0aa-9f9227f775d2
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiauDbgWarning function [Imaging Devices], wiautil/wiauDbgWarning, image.wiaudbgwarning, wiauFncs_1248626b-0d4f-445c-855c-9ba477cf306c.xml, wiauDbgWarning
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
-	wiauDbgWarning
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# wiauDbgWarning function
The <b>wiauDbgWarning</b> function logs a warning message.

## Syntax

````
inline void __stdcall wiauDbgWarning(
   LPCSTR   fname,
   LPCSTR   fmt, ...
);
````

## Parameters

`fname`

Pointer to a string containing the name of the function or method into which the call to <b>wiauDbgWarning</b> is inserted.

`fmt`

TBD

`Arg1`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later. Available in Windows XP and later. |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\wiautil\nf-wiautil-wiaudbgerror.md">wiauDbgError</a>



<a href="..\wiautil\nf-wiautil-wiaudbgdump.md">wiauDbgDump</a>



<a href="..\wiautil\nf-wiautil-wiaudbgerrorhr.md">wiauDbgErrorHr</a>



<a href="..\wiautil\nf-wiautil-wiaudbgtrace.md">wiauDbgTrace</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauDbgWarning function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>