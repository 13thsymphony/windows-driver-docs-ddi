---
UID: NF:wdbgexts.GetCurrentProcessHandle
title: GetCurrentProcessHandle function
author: windows-driver-content
description: The GetCurrentProcessHandle function returns the system handle for the current process.
old-location: debugger\getcurrentprocesshandle.htm
old-project: debugger
ms.assetid: b6780f1c-e093-4d91-8909-dabb1ecaefaa
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: wdbgexts/GetCurrentProcessHandle, WdbgExts_Ref_50cc8e27-7f7e-4ec3-ad2d-745f38e87037.xml, IDebugSystemObjects2::GetCurrentProcessHandle, IDebugSystemObjects2, debugger.getcurrentprocesshandle, IDebugSystemObjects3, IDebugSystemObjects3::GetCurrentProcessHandle, GetCurrentProcessHandle, GetCurrentProcessHandle function [Windows Debugging], IDebugSystemObjects, IDebugSystemObjects::GetCurrentProcessHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdbgexts.h
apiname:
-	GetCurrentProcessHandle
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---


# GetCurrentProcessHandle function
The <b>GetCurrentProcessHandle</b> function returns the system handle for the current process.

## Syntax

````
__inline VOID GetCurrentProcessHandle(
   PHANDLE hp
);
````

## Parameters

`hp`




## Return Value

None

## Remarks

In kernel-mode debugging, the only process in the target is the virtual process created for the kernel. In this case, an artificial handle is created. The artificial handle can only be used with the debugger.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdbgexts.h (include Wdbgexts.h, Dbgeng.h) |
| **Library** | NtosKrnl.exe |