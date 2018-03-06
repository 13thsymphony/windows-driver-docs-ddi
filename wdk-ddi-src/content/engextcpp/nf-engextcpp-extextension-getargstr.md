---
UID: NF:engextcpp.ExtExtension.GetArgStr
title: ExtExtension::GetArgStr method
author: windows-driver-content
description: The GetArgStr method returns a named string argument from the command line used to invoke the current extension command.
old-location: debugger\getargstr.htm
old-project: debugger
ms.assetid: a875b832-11dc-4cba-8fce-019bbb9ec7f2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: EngExtCpp_Ref_0a1f3246-41a5-4a2f-8656-45f8c17b6418.xml, ExtExtension, ExtExtension class [Windows Debugging], GetArgStr method, ExtExtension::GetArgStr, GetArgStr method [Windows Debugging], GetArgStr method [Windows Debugging], ExtExtension class, GetArgStr,ExtExtension.GetArgStr, debugger.getargstr
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
req.lib: engextcpp.hpp
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
-	ExtExtension.GetArgStr
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# GetArgStr method
The <b>GetArgStr</b> method returns a named string argument from the command line used to invoke the current extension command.

## Syntax

````
PCSTR GetArgStr(
  [in] PCSTR Name,
  [in] bool  Required
);
````

## Parameters

`Name`

Specifies the name of the argument.  The command-line description used in <a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a> must specify that the type of this argument is string.

`Required`

Specifies if the argument is required.  If <i>Required</i> is <code>true</code> and the argument was not present on the command line, <b>ExtInvalidArgumentException</b> is thrown.  You do not need to set this parameter; if it is not set <i>Required</i> defaults to <code>true</code>.


## Return Value

<b>GetArgStr</b> returns the named string argument.

## Remarks

For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553340">Parsing Extension Arguments</a>.

The string returned by <b>GetArgStr</b> is only meaningful during the execution of the current extension command.

This method should only be called during the execution of an extension command provided by this class.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |
| **Library** | engextcpp.hpp |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



<a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtExtension.GetArgStr method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>