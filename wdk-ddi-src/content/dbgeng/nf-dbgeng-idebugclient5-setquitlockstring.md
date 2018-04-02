---
UID: NF:dbgeng.IDebugClient5.SetQuitLockString
title: IDebugClient5::SetQuitLockString method
author: windows-driver-content
description: Sets a quit lock string.
old-location: debugger\idebugclient5_setquitlockstring.htm
old-project: debugger
ms.assetid: 0C4888C7-B7F9-4B23-8AC9-41CB7863AF22
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugClient5, IDebugClient5 interface [Windows Debugging], SetQuitLockString method, IDebugClient5::SetQuitLockString, SetQuitLockString method [Windows Debugging], SetQuitLockString method [Windows Debugging], IDebugClient5 interface, SetQuitLockString,IDebugClient5.SetQuitLockString, dbgeng/IDebugClient5::SetQuitLockString, debugger.idebugclient5_setquitlockstring
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugClient5.SetQuitLockString
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugClient5::SetQuitLockString method
Sets a quit lock string.

## Syntax

```
HRESULT SetQuitLockString(
  PCSTR String
);
```

## Parameters

`String`

A pointer to the quit lock string.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

This function provides control over locking the session against
    undesired quits.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>