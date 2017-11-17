---
UID: NF.dbgeng.IDebugSymbols3.AppendImagePath
title: IDebugSymbols3::AppendImagePath
author: windows-driver-content
description: The AppendImagePath method appends directories to the executable image path.
old-location: debugger\appendimagepath.htm
ms.assetid: faafc6d0-f311-46c1-87c1-8b0ea20984db
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: debugger
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugSymbols.AppendImagePath,IDebugSymbols2.AppendImagePath,IDebugSymbols3.AppendImagePath
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
ms.keywords: IDebugSymbols3, AppendImagePath, IDebugSymbols3::AppendImagePath
req.iface: IDebugSymbols3
---

# IDebugSymbols3::AppendImagePath method



## -description
<p>The <b>AppendImagePath</b>  method appends directories to the executable image path.</p>


## -syntax

````
HRESULT AppendImagePath(
  [in] PCSTR Addition
);
````


## -parameters
<dl>

### -param <i>Addition</i> [in]

<dd>
<p>Specifies the directories to append to the executable image path.  This is a string that contains directory names separated by semicolons (;).</p>
</dd>
</dl>

## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p>

## -remarks
<p>The executable image path is used by the <a href="debugger.e#engine#engine"><i>engine</i></a> when searching for executable images.</p>

<p>The executable image path can consist of several directories separated by semicolons (;).  These directories are searched in order.</p>

<p>The executable image path is used by the <a href="debugger.e#engine#engine"><i>engine</i></a> when searching for executable images.</p>

<p>The executable image path can consist of several directories separated by semicolons (;).  These directories are searched in order.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546851">GetImagePath</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556708">SetImagePath</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::AppendImagePath method%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
