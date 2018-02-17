---
UID: NF:wiautil.wiauDbgSetFlags
title: wiauDbgSetFlags macro
author: windows-driver-content
description: The wiauDbgSetFlags function sets debugging flags.
old-location: image\wiaudbgsetflags.htm
old-project: image
ms.assetid: e3b944ef-daa5-412c-ac11-7b08d2b9333b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiauDbgSetFlags function [Imaging Devices], wiauFncs_d0f9a6a3-6958-44cb-9467-7f6413f95ca7.xml, wiauDbgSetFlags, image.wiaudbgsetflags, wiautil/wiauDbgSetFlags
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wiautil.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wiautil.h
apiname:
-	wiauDbgSetFlags
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# wiauDbgSetFlags function
The <b>wiauDbgSetFlags</b> function sets debugging flags.

## Syntax

````
inline DWORD __stdcall wiauDbgSetFlags(
   DWORD flags
);
````

## Parameters

`flags`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h) |
| **Library** | wiautil.h |

## See Also

<a href="..\wiautil\nf-wiautil-wiaudbgflags.md">wiauDbgFlags</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiauDbgSetFlags function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>