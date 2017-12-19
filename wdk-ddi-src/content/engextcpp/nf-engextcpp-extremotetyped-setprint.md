---
UID: NF.engextcpp.ExtRemoteTyped.SetPrint
title: ExtRemoteTyped::SetPrint method
author: windows-driver-content
description: The SetPrint method sets the typed data represented by the ExtRemoteTyped object by formatting an expression and then evaluating that expression.
old-location: debugger\extremotetyped_setprint.htm
old-project: Debugger
ms.assetid: ae478779-8ec1-4a50-a37c-3017aca2c912
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ExtRemoteTyped, ExtRemoteTyped::SetPrint, SetPrint
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
req.alt-api: ExtRemoteTyped.SetPrint
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
---

# ExtRemoteTyped::SetPrint method



## -description
The <b>SetPrint</b> method sets the typed data represented by the <a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a> object by formatting an expression and then evaluating that expression.



## -syntax

````
void SetPrint(
  [in] CPSTR Format,
             ...
);
````


## -parameters

### -param Format [in]

The format string used to create the expression.  This is the same as the format string used by the C <b>printf</b> function.

<div class="alert"><b>Note</b>   While other methods and functions in the debugger engine API provide additional, debugger-specific conversion characters, <b>SetPrint</b> only supports the conversion characters used by <b>printf</b>.</div>
<div> </div>

### -param ... 

The arguments for the format string, as in <b>printf</b>.  The arguments should match the conversion characters in <i>Format</i>.


## -returns
This method does not return a value.


## -remarks


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
<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>
</dt>
<dt>
<a href="debugger.extremotetyped_set_bool">ExtRemoteTyped::Set(bool)</a>
</dt>
<dt>
<a href="debugger.extremotetyped_set_pcstr">ExtRemoteTyped::Set(pcstr)</a>
</dt>
<dt>
<a href="debugger.extremotetyped_set_pcstr_ulong64">ExtRemoteTyped::Set(pcstr ulong64)</a>
</dt>
<dt>
<a href="debugger.extremotetyped_set_pcstr_ulong64_bool">ExtRemoteTyped::Set(pcstr ulong64 bool)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20ExtRemoteTyped.SetPrint method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

