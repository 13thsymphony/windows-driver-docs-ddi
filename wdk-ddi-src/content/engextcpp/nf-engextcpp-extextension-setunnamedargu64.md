---
UID: NF:engextcpp.ExtExtension.SetUnnamedArgU64
title: ExtExtension::SetUnnamedArgU64 method
author: windows-driver-content
description: The SetUnnamedArgU64 method sets the value of an unnamed expression argument for the current extension command.
old-location: debugger\setunnamedargu64.htm
old-project: debugger
ms.assetid: 27f25bba-8118-47c0-9b9d-6b0a1ceb4b8e
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: EngExtCpp_Ref_65080cf5-2492-440b-a496-869faf8c9c49.xml, ExtExtension, ExtExtension class [Windows Debugging], SetUnnamedArgU64 method, ExtExtension::SetUnnamedArgU64, SetUnnamedArgU64 method [Windows Debugging], SetUnnamedArgU64 method [Windows Debugging], ExtExtension class, SetUnnamedArgU64,ExtExtension.SetUnnamedArgU64, debugger.setunnamedargu64
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
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
-	Engextcpp.hpp
api_name:
-	ExtExtension.SetUnnamedArgU64
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# ExtExtension~r1::SetUnnamedArgU64 method
The <b>SetUnnamedArgU64</b> method sets the value of an unnamed expression argument for the current extension command.

## Syntax

```
bool  throw() SetUnnamedArgU64(
  ULONG   Index,
  ULONG64 Arg,
  bool    OnlyIfUnset
);
```

## Parameters

`Index`

Specifies the index of the argument.  The command-line description used in <a href="https://msdn.microsoft.com/library/windows/hardware/ff544514">EXT_COMMAND</a> must specify that the type of this argument is expression.  <i>Index</i> should be between zero and the number of unnamed arguments - as specified in the command-line description used in EXT_COMMAND - minus one.

`Arg`

Specifies the value of an unnamed expression argument.

`OnlyIfUnset`

Specifies what happens if the argument is already set.  If <i>OnlyIfUnset</i> is <code>true</code> and the argument has already been set, the argument will not be changed.  If <i>OnlyIfUnset</i> is <code>false</code> and the argument has already been set, the argument will be changed.


## Return Value

<b>SetUnnamedArgU64</b> returns <code>true</code> if the argument was changed; <code>false</code> otherwise.

## Remarks

For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553340">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544514">EXT_COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>