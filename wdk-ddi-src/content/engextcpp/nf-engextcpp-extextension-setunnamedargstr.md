---
UID: NF.engextcpp.ExtExtension.SetUnnamedArgStr
title: ExtExtension::SetUnnamedArgStr method
author: windows-driver-content
description: The SetUnnamedArgStr method sets an unnamed string argument for the current extension command.
old-location: debugger\setunnamedargstr.htm
old-project: Debugger
ms.assetid: 96e309ca-1267-4a5d-97c6-1b15de9190d5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ExtExtension, ExtExtension::SetUnnamedArgStr, SetUnnamedArgStr
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
req.alt-api: ExtExtension.SetUnnamedArgStr
req.alt-loc: Engextcpp.hpp
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
---

# ExtExtension::SetUnnamedArgStr method



## -description
The <b>SetUnnamedArgStr</b> method sets an unnamed string argument for the current extension command.



## -syntax

````
bool SetUnnamedArgStr(
  [in] ULONG Index,
  [in] PCSTR Arg,
  [in] bool  OnlyIfUnset
);
````


## -parameters

### -param Index [in]

Specifies the index of the argument.  The command-line description used in <a href="debugger.ext_command">EXT_COMMAND</a> must specify that the type of this argument is string.  <i>Index</i> should be between zero and the number of unnamed arguments - as specified in the command-line description used in EXT_COMMAND - minus one.


### -param Arg [in]

A string that specifies the value of the unnamed argument.  A pointer to the first non-space character is saved as the argument.


### -param OnlyIfUnset [in]

Specifies what happens if the argument is already set.  If <i>OnlyIfUnset</i> is <code>true</code> and the argument has already been set, the argument will not be changed.  If <i>OnlyIfUnset</i> is <code>false</code> and the argument has already been set, the argument will be changed.


## -returns
<b>SetUnnamedArgStr</b> returns <code>true</code> if the argument was changed; <code>false</code> otherwise.


## -remarks
For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553340">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Engextcpp.hpp (include Engextcpp.hpp)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="debugger.extextension">ExtExtension</a>
</dt>
<dt>
<a href="debugger.ext_command">EXT_COMMAND</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20ExtExtension.SetUnnamedArgStr method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

