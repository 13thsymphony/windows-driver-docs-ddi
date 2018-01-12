---
UID: NF:dbgeng.IDebugSymbols3.AppendSymbolPath
title: IDebugSymbols3::AppendSymbolPath method
author: windows-driver-content
description: The AppendSymbolPath method appends directories to the symbol path.
old-location: debugger\appendsymbolpath.htm
old-project: debugger
ms.assetid: 99a0ded5-2a73-40c9-99f4-82d31395aa62
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3::AppendSymbolPath, AppendSymbolPath
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugSymbols.AppendSymbolPath,IDebugSymbols2.AppendSymbolPath,IDebugSymbols3.AppendSymbolPath
req.alt-loc: Dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugSymbols3::AppendSymbolPath method



## -description
The <b>AppendSymbolPath</b>  method appends directories to the symbol path.



## -syntax

````
HRESULT AppendSymbolPath(
  [in] PCSTR Addition
);
````


## -parameters

### -param Addition [in]

Specifies the directories to append to the symbol path.  This is a string that contains symbol path elements separated by semicolons (;).  Each symbol path element can specify either a directory or a symbol server.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
For more information about manipulating the symbol path, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560150">Using Symbols</a>.  For an overview of the symbol path and its syntax, see <a href="https://msdn.microsoft.com/705df98f-717f-40ad-a424-101826970691">Symbol Path</a>.


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
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549155">GetSymbolPath</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556802">SetSymbolPath</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::AppendSymbolPath method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

