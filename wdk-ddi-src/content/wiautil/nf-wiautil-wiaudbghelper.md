---
UID : NF:wiautil.wiauDbgHelper
title : wiauDbgHelper function
author : windows-driver-content
description : The wiauDbgHelper function formats a message and writes it to a log file, or debugger, or both.
old-location : image\wiaudbghelper.htm
old-project : image
ms.assetid : 5be1ede7-13a0-4ef4-93bd-8a1adc5baa9e
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : wiauDbgHelper function [Imaging Devices], wiautil/wiauDbgHelper, image.wiaudbghelper, wiauDbgHelper, wiauFncs_be2f3b11-e1a0-4728-856e-ce686344f166.xml
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


# wiauDbgHelper function
The <b>wiauDbgHelper</b> function formats a message and writes it to a log file, or debugger, or both.

## Syntax

````
void __stdcall wiauDbgHelper(
  _In_ LPCSTR  prefix,
  _In_ LPCSTR  fname,
  _In_ LPCSTR  fmt,
       va_list marker
);
````

## Parameters

`prefix`

Pointer to a string containing a prefix (such as "ERROR " or "WARN ") associated with the message.

`fname`

Pointer to a string containing the name of the function or method into which the call to <b>wiauDbgHelper</b> is inserted.

`fmt`

Pointer to a string that controls how an item or items in a variable argument list is to be formatted.

`marker`

Marks the beginning of a variable argument list.


## Return Value

None

## Remarks

The <b>wiauDbgHelper</b> function is a general-purpose function that is used internally by many of the other <b>wiauDbg</b><b><i>Xxx</i></b> functions. While it can be used in WIA minidrivers, there are other limited-purpose functions provided that are more convenient to use.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later. Available in Windows XP and later. |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\wiautil\nf-wiautil-wiaudbgdump.md">wiauDbgDump</a>

<a href="..\wiautil\nf-wiautil-wiaudbgerror.md">wiauDbgError</a>

<a href="..\wiautil\nf-wiautil-wiaudbgerrorhr.md">wiauDbgErrorHr</a>

<a href="..\wiautil\nf-wiautil-wiaudbgwarning.md">wiauDbgWarning</a>

<a href="..\wiautil\nf-wiautil-wiaudbgtrace.md">wiauDbgTrace</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauDbgHelper function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>