---
UID: NF:dbgeng.IDebugClient.GetOutputLinePrefix
title: IDebugClient::GetOutputLinePrefix method
author: windows-driver-content
description: Gets the prefix used for multiple lines of output.
old-location: debugger\idebugclient_getoutputlineprefix.htm
old-project: debugger
ms.assetid: FE836B10-1782-4B0E-9D4B-2740FE94B6E1
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetOutputLinePrefix method [Windows Debugging], GetOutputLinePrefix method [Windows Debugging], IDebugClient interface, GetOutputLinePrefix,IDebugClient.GetOutputLinePrefix, IDebugClient, IDebugClient interface [Windows Debugging], GetOutputLinePrefix method, IDebugClient::GetOutputLinePrefix, dbgeng/IDebugClient::GetOutputLinePrefix, debugger.idebugclient_getoutputlineprefix
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
-	dbgeng.h
api_name:
-	IDebugClient.GetOutputLinePrefix
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetOutputLinePrefix method
Gets the prefix used for multiple lines of output.

## Syntax

````
HRESULT GetOutputLinePrefix(
  [out]           writes_opt_(BufferSize) PSTR Buffer,
  [in]            ULONG                        BufferSize,
  [out, optional] PULONG                       PrefixSize
);
````

## Parameters

`Buffer`

A pointer to the buffer to get the prefix.

`BufferSize`

The size of the buffer.

`PrefixSize`

A pointer to the size of the buffer.


## Return Value

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
</table>

## Remarks

Some of the engine commands produce
    multiple lines of output.  A prefix can be added to each line. 

 The prefix value  is not a general setting for any output
    that contains a newline. Methods which use
    the line prefix are marked in their documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>