---
UID: NF:wiautil.wiauDbgLegacyWarning
title: wiauDbgLegacyWarning function
author: windows-driver-content
description: The wiauDbgLegacyWarning function logs a warning message.
old-location: image\wiaudbglegacywarning.htm
old-project: image
ms.assetid: 5da7c762-ad5c-45bd-aebe-dc3526005569
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: image.wiaudbglegacywarning, wiauDbgLegacyWarning, wiauDbgLegacyWarning function [Imaging Devices], wiauFncs_03dcc80b-0d36-4130-a05d-bb407cd813cb.xml, wiautil/wiauDbgLegacyWarning
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
-	wiauDbgLegacyWarning
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# wiauDbgLegacyWarning function
The <b>wiauDbgLegacyWarning</b> function logs a warning message.

## Syntax

```
void wiauDbgLegacyWarning(
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

The <b>wiauDbgLegacyWarning</b> function is identical to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550163">wiauDbgWarning</a> function except that the latter has a parameter used to identify the function or method that is active when the function is called.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550163">wiauDbgWarning</a>