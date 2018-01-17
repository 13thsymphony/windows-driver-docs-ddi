---
UID: NF:engextcpp.ExtExtension.GetRawArgStr
title: ExtExtension::GetRawArgStr method
author: windows-driver-content
description: The GetRawArgStr method returns a string that represents the arguments passed to the extension command.
old-location: debugger\getrawargstr.htm
old-project: debugger
ms.assetid: 677b56ee-3758-4f47-9f8e-fc8878d00136
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ExtExtension, ExtExtension::GetRawArgStr, GetRawArgStr
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
req.alt-api: ExtExtension.GetRawArgStr
req.alt-loc: engextcpp.hpp
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
req.typenames: *PDRMRIGHTS, DRMRIGHTS
---

# ExtExtension::GetRawArgStr method



## -description
The <b>GetRawArgStr</b> method returns a string that represents the arguments passed to the extension command.



## -syntax

````
PCSTR GetRawArgStr();
````


## -parameters


## -returns
<b>GetRawArgStr</b> returns a string that represents the arguments passed to the extension command.  In particular, if the extension command was called from a command line, this string contains the portion of the command line that follows the extension command.  The return value can be <b>NULL</b> or empty.

<b>GetRawArgStr</b> returns a string that represents the arguments passed to the extension command.  In particular, if the extension command was called from a command line, this string contains the portion of the command line that follows the extension command.  The return value can be <b>NULL</b> or empty.

<b>GetRawArgStr</b> returns a string that represents the arguments passed to the extension command.  In particular, if the extension command was called from a command line, this string contains the portion of the command line that follows the extension command.  The return value can be <b>NULL</b> or empty.


## -remarks
For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553340">Parsing Extension Arguments</a>.

The string returned by this method is only meaningful during the execution of the current extension command.

This method should only be called during the execution of an extension command provided by this class.</p>