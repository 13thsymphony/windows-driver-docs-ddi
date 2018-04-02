---
UID: NF:engextcpp.ExtExtension.GetUnnamedArgStr
title: ExtExtension::GetUnnamedArgStr method
author: windows-driver-content
description: The GetUnnamedArgStr method returns an unnamed string argument from the command line used to invoke the current extension command.
old-location: debugger\getunnamedargstr.htm
old-project: debugger
ms.assetid: 2aaaee0d-eabe-4615-b888-8239f2791d80
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: EngExtCpp_Ref_68f021ae-574a-4bc5-bea2-545f59b8ea74.xml, ExtExtension, ExtExtension class [Windows Debugging], GetUnnamedArgStr method, ExtExtension::GetUnnamedArgStr, GetUnnamedArgStr method [Windows Debugging], GetUnnamedArgStr method [Windows Debugging], ExtExtension class, GetUnnamedArgStr,ExtExtension.GetUnnamedArgStr, debugger.getunnamedargstr
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
-	ExtExtension.GetUnnamedArgStr
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# ExtExtension~r1::GetUnnamedArgStr method
The <b>GetUnnamedArgStr</b> method returns an unnamed string argument from the command line used to invoke the current extension command.

## Syntax

```
PCSTR  throw() GetUnnamedArgStr(
  ULONG Index
);
```

## Parameters

`Index`

Specifies the index of the argument.  The command-line description used in <a href="https://msdn.microsoft.com/library/windows/hardware/ff544514">EXT_COMMAND</a> must specify that the type of this argument is string.  The value of <i>Index</i> should be between zero and the number of unnamed arguments returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff548001">GetNumUnnamedArgs</a> minus one (unnamed arguments - 1).


## Return Value

<b>GetUnnamedArgStr</b> returns the unnamed string argument.

## Remarks

For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553340">Parsing Extension Arguments</a>.

The string returned by <b>GetUnnamedArgStr</b> is only meaningful during the execution of the current extension command.

This method should only be called during the execution of an extension command provided by this class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544514">EXT_COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548001">GetNumUnnamedArgs</a>