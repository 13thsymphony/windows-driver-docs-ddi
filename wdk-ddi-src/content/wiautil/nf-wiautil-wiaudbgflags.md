---
UID: NF:wiautil.wiauDbgFlags
title: wiauDbgFlags function
author: windows-driver-content
description: The wiauDbgFlags function determines whether a particular debugging flag is set.
old-location: image\wiaudbgflags.htm
old-project: image
ms.assetid: 2185a1c0-e952-4dbd-b1a9-82339e417774
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: image.wiaudbgflags, wiauDbgFlags, wiauDbgFlags function [Imaging Devices], wiauFncs_db71e773-84d8-40b9-9688-9fa33aad9182.xml, wiautil/wiauDbgFlags
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wiautil.h
api_name:
-	wiauDbgFlags
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# wiauDbgFlags function
The <b>wiauDbgFlags</b> function determines whether a particular debugging flag is set.

## Syntax

````
inline void __stdcall wiauDbgFlags(
   DWORD    flags,
   LPCSTR   prefix,
   LPCSTR   fname,
   LPCSTR   fmt, ...
);
````

## Parameters

`flags`

Is a set of flags that control which information is placed in the log file or displayed in the debugger. See the <i>flags</i> parameter of <a href="..\wiautil\nf-wiautil-wiaudbgsetflags.md">wiauDbgSetFlags</a> for a list of the flag values.

`prefix`

Pointer to a string containing a prefix (such as "ERROR " or "WARN ").

`fname`

Pointer to a string containing the name of the function or method into which the call to <b>wiauDbgDump</b> is inserted.

`fmt`

TBD

`Arg1`




## Return Value

None

## Remarks

If message logging to log file, or debugger, or both is enabled and the particular flag in the <i>flags</i> parameter is enabled, this function logs a message containing the strings pointed to by the <i>prefix</i>, <i>fname</i>, and <i>fmt</i> parameters.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\wiautil\nf-wiautil-wiaudbgsetflags.md">wiauDbgSetFlags</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauDbgFlags function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>