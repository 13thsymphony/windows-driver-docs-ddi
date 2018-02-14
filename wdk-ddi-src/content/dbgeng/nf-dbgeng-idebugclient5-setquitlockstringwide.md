---
UID: NF:dbgeng.IDebugClient5.SetQuitLockStringWide
title: IDebugClient5::SetQuitLockStringWide method
author: windows-driver-content
description: Sets a quit lock Unicode character string.
old-location: debugger\idebugclient5_setquitlockstringwide.htm
old-project: debugger
ms.assetid: B9A2C636-BF18-4D1B-A013-8CAE65FCC56F
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: SetQuitLockStringWide method [Windows Debugging], IDebugClient5 interface [Windows Debugging], SetQuitLockStringWide method, IDebugClient5, debugger.idebugclient5_setquitlockstringwide, SetQuitLockStringWide, dbgeng/IDebugClient5::SetQuitLockStringWide, SetQuitLockStringWide method [Windows Debugging], IDebugClient5 interface, IDebugClient5::SetQuitLockStringWide
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugClient5.SetQuitLockStringWide
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# SetQuitLockStringWide method
Sets a quit lock Unicode character string.

## Syntax

````
HRESULT SetQuitLockStringWide(
  [in] PCWSTR String
);
````

## Parameters

`String`

A pointer to the quit lock Unicode character string.


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
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::SetQuitLockStringWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>