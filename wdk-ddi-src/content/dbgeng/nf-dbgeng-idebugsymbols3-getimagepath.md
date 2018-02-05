---
UID : NF:dbgeng.IDebugSymbols3.GetImagePath
title : IDebugSymbols3::GetImagePath method
author : windows-driver-content
description : The GetImagePath method returns the executable image path.
old-location : debugger\getimagepath.htm
old-project : debugger
ms.assetid : 9310dc82-b80f-45bb-9d8a-1239330bc799
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : dbgeng/IDebugSymbols::GetImagePath, IDebugSymbols2::GetImagePath, GetImagePath method [Windows Debugging], IDebugSymbols2 interface, IDebugSymbols_9d38f509-e800-4090-901b-6dc78710c15f.xml, GetImagePath, GetImagePath method [Windows Debugging], IDebugSymbols::GetImagePath, dbgeng/IDebugSymbols2::GetImagePath, IDebugSymbols2 interface [Windows Debugging], GetImagePath method, IDebugSymbols interface [Windows Debugging], GetImagePath method, debugger.getimagepath, IDebugSymbols3 interface [Windows Debugging], GetImagePath method, GetImagePath method [Windows Debugging], IDebugSymbols interface, IDebugSymbols3::GetImagePath, GetImagePath method [Windows Debugging], IDebugSymbols3 interface, dbgeng/IDebugSymbols3::GetImagePath, IDebugSymbols3
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
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
req.lib : dbgeng.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetImagePath method
The <b>GetImagePath</b>  method returns the executable image path.

## Syntax

````
HRESULT GetImagePath(
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG PathSize
);
````

## Parameters

`Buffer`

Receives the executable image path.  This is a string that contains directories separated by semicolons (<b>;</b>).  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

`BufferSize`

Specifies the size, in characters, of the <i>Buffer</i> buffer.

`PathSize`

Receives the size, in characters, of the executable image path.


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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful. However, the buffer was not large enough to hold the executable image path and the path was truncated.

</td>
</tr>
</table>

## Remarks

The executable image path is used by the engine when searching for executable images.

The executable image path can consist of several directories separated by semicolons.  These directories are searched in order.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538092">AppendImagePath</a>

<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>

<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556708">SetImagePath</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::GetImagePath method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>