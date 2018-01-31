---
UID : NC:wdbgexts.PWINDBG_EXTENSION_DLL_INIT
title : PWINDBG_EXTENSION_DLL_INIT
author : windows-driver-content
description : The PWINDBG_EXTENSION_DLL_INIT ( WinDbgExtensionDllInit) callback function is used to load and initialize the extension module.
old-location : debugger\windbgextensiondllinit.htm
old-project : debugger
ms.assetid : 1c97ac8c-9b40-44e8-b669-6b7d4ee2d671
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : debugger.windbgextensiondllinit, WinDbgExtensionDllInit, WinDbgExtensionDllInit callback function [Windows Debugging], WinDbgExtensionDllInit, PWINDBG_EXTENSION_DLL_INIT, PWINDBG_EXTENSION_DLL_INIT, wdbgexts/WinDbgExtensionDllInit, WdbgExts_Callbacks_18383848-27f2-4d4e-a5b0-c6ce27377687.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdbgexts.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
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
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : VPCI_WRITE_BLOCK_INPUT, *PVPCI_WRITE_BLOCK_INPUT
req.product : Windows 10 or later.
---


# PWINDBG_EXTENSION_DLL_INIT callback function
The <b>PWINDBG_EXTENSION_DLL_INIT</b> (<b> WinDbgExtensionDllInit</b>) callback function is used to load and initialize the extension module.

## Syntax

```
PWINDBG_EXTENSION_DLL_INIT PwindbgExtensionDllInit;

void PwindbgExtensionDllInit(
  PWINDBG_EXTENSION_APIS lpExtensionApis,
  USHORT MajorVersion,
  USHORT MinorVersion
)
{...}
```

## Parameters

`lpExtensionApis`

A pointer to a WINDBG_EXTENSION_APIS64 structure, which contains  pointers to functions that you can use for standard operations. Copy the entire structure to a global variable in your DLL. For example, you could create a  global variable named ExtensionApis as shown in the following example.
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>WINDBG_EXTENSION_APIS64   ExtensionApis;</pre>
</td>
</tr>
</table></span></div>

`MajorVersion`

Specifies the Microsoft Windows build type. A value of 0xC indicates the checked build of Windows. A value of 0xF indicates the free build of Windows.   Save this value in a global variable in your DLL. For example, you could create a global variable named SavedMajorVersion.

`MinorVersion`

Specifies the Windows build number (for example 2600) of the target system. Save this value in a global variable in your DLL. For example, you could create a global variable named SavedMinorVersion.


## Return Value

None

## Remarks

<i>WinDbgExtensionDllInit</i> is called by the debugger when the extension DLL is loaded.

It is recommended that you always use 64-bit pointers in your code, since the debugger will automatically resize these pointers when necessary. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff537780">32-Bit Pointers and 64-Bit Pointers</a> for details. However, if you choose to use 32-bit pointers, the first parameter of <i>WinDbgExtensionDllInit</i> will have the type PWINDBG_EXTENSION_APIS instead of PWINDBG_EXTENSION_APIS64.

For more details, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560220">Using WdbgExts Extension Callbacks</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdbgexts.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |