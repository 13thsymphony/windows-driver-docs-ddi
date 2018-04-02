---
UID: NF:wiautil.wiauDbgLegacyTrace
title: wiauDbgLegacyTrace function
author: windows-driver-content
description: The wiauDbgLegacyTrace function logs a trace message.
old-location: image\wiaudbglegacytrace.htm
old-project: image
ms.assetid: ccbcab46-0af9-4c21-896f-14096f1461bc
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiaudbglegacytrace, wiauDbgLegacyTrace, wiauDbgLegacyTrace function [Imaging Devices], wiauFncs_a780f296-5780-4589-9aa6-1e61ebec013e.xml, wiautil/wiauDbgLegacyTrace
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: This function is available in Windows XP and later.
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
-	wiauDbgLegacyTrace
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# wiauDbgLegacyTrace function
The <b>wiauDbgLegacyTrace</b> function logs a trace message.

## Syntax

```
void wiauDbgLegacyTrace(
  LPCSTR fmt,
  ...    
);
```

## Parameters

`fmt`

TBD

`Arg1`




## Return Value

None

## Remarks

The <b>wiauDbgLegacyTrace</b> function is identical to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550161">wiauDbgTrace</a> function except that the latter has a parameter used to identify the function or method that is active when the function is called.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This function is available in Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550161">wiauDbgTrace</a>