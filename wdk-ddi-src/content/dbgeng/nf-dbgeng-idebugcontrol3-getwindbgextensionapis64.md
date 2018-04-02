---
UID: NF:dbgeng.IDebugControl3.GetWindbgExtensionApis64
title: IDebugControl3::GetWindbgExtensionApis64 method
author: windows-driver-content
description: The GetWindbgExtensionApis64 method returns a structure that facilitates using the WdbgExts API.
old-location: debugger\getwindbgextensionapis64.htm
old-project: debugger
ms.assetid: 01b34b26-2835-4a58-abf3-190da63d25eb
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetWindbgExtensionApis64 method [Windows Debugging], GetWindbgExtensionApis64 method [Windows Debugging], IDebugControl interface, GetWindbgExtensionApis64 method [Windows Debugging], IDebugControl2 interface, GetWindbgExtensionApis64 method [Windows Debugging], IDebugControl3 interface, GetWindbgExtensionApis64,IDebugControl3.GetWindbgExtensionApis64, IDebugControl interface [Windows Debugging], GetWindbgExtensionApis64 method, IDebugControl2 interface [Windows Debugging], GetWindbgExtensionApis64 method, IDebugControl2::GetWindbgExtensionApis64, IDebugControl3, IDebugControl3 interface [Windows Debugging], GetWindbgExtensionApis64 method, IDebugControl3::GetWindbgExtensionApis64, IDebugControl::GetWindbgExtensionApis64, IDebugControl_51215e32-dcd3-440f-92ee-6ff82ae1c8e6.xml, dbgeng/IDebugControl2::GetWindbgExtensionApis64, dbgeng/IDebugControl3::GetWindbgExtensionApis64, dbgeng/IDebugControl::GetWindbgExtensionApis64, debugger.getwindbgextensionapis64
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Wdbgexts.h, Dbgeng.h, Wdbgexts.h
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
-	IDebugControl.GetWindbgExtensionApis64
-	IDebugControl2.GetWindbgExtensionApis64
-	IDebugControl3.GetWindbgExtensionApis64
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugControl3::GetWindbgExtensionApis64 method
The <b>GetWindbgExtensionApis64</b> method returns a structure that facilitates using the WdbgExts API.

## Syntax

```
HRESULT GetWindbgExtensionApis64(
  PWINDBG_EXTENSION_APIS64 Api
);
```

## Parameters

`Api`

Receives a WINDBG_EXTENSION_APIS64 structure.  This structure contains the functions used by the WdbgExts API.  The <b>nSize</b> member of this structure must be set to the size of the structure before it is passed to this method.


## Return Value

This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The value of <i>Api</i>-&gt;<b>nSize</b> does not equal the size of the structure WINDBG_EXTENSION_APIS64.

</td>
</tr>
</table>

## Remarks

If you are including Wdbgexts.h in your extension code, you should call this method during the initialization of the extension DLL (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540476">DebugExtensionInitialize</a>).

Many WdbgExts functions are really macros.  To ensure that these macros work correctly, the structure received by the <i>Api</i> parameter should be stored in a global variable named <b>ExtensionApis</b>.  

The WINDBG_EXTENSION_APIS64 structure returned by this method serves the same purpose as the one provided to the callback function <a href="https://msdn.microsoft.com/library/windows/hardware/ff561303">WinDbgExtensionDllInit</a> (used by WdbgExts extensions).

For a list of the functions provided by the WdbgExts API, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561258">WdbgExts Functions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Wdbgexts.h, Dbgeng.h, Wdbgexts.h) |