---
UID : NF:dbgeng.IDebugControl4.GetProcessorTypeNamesWide
title : IDebugControl4::GetProcessorTypeNamesWide method
author : windows-driver-content
description : The GetProcessorTypeNamesWide method returns the full name and abbreviated name of the specified processor type.
old-location : debugger\getprocessortypenameswide.htm
old-project : debugger
ms.assetid : 24787963-98c6-4c32-9ba8-2cd4778f8436
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : GetProcessorTypeNamesWide method [Windows Debugging], IDebugControl4 interface, IDebugControl4 interface [Windows Debugging], GetProcessorTypeNamesWide method, GetProcessorTypeNamesWide method [Windows Debugging], IDebugControl4::GetProcessorTypeNamesWide, GetProcessorTypeNamesWide, debugger.getprocessortypenameswide, IDebugControl4, dbgeng/IDebugControl4::GetProcessorTypeNamesWide
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


# GetProcessorTypeNamesWide method
The <b>GetProcessorTypeNamesWide</b>  method returns the full name and abbreviated name of the specified processor type.

## Syntax

````
HRESULT GetProcessorTypeNamesWide(
  [in]            ULONG  Type,
  [out, optional] PWSTR  FullNameBuffer,
  [in]            ULONG  FullNameBufferSize,
  [out, optional] PULONG FullNameSize,
  [out, optional] PWSTR  AbbrevNameBuffer,
  [in]            ULONG  AbbrevNameBufferSize,
  [out, optional] PULONG AbbrevNameSize
);
````

## Parameters

`Type`

Specifies the type of the processor whose name is requested.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff545572">GetActualProcessorType</a> for a list of possible values.

`FullNameBuffer`

Receives the full name of the processor type.  If <i>FullNameBuffer</i> is <b>NULL</b>, this information is not returned.

`FullNameBufferSize`

Specifies the size, in characters, of the buffer that <i>FullNameBuffer</i> specifies.

`FullNameSize`

Receives the size in characters of the full name of the processor type.  If <i>FullNameSize</i> is <b>NULL</b>, this information is not returned.

`AbbrevNameBuffer`

Receives the abbreviated name of the processor type.  If <i>AbbrevNameBuffer</i> is <b>NULL</b>, this information is not returned.

`AbbrevNameBufferSize`

Specifies the size, in characters, of the buffer that <i>AbbrevNameBuffer</i> specifies.

`AbbrevNameSize`

Receives the size in characters of the abbreviated name of the processor type.  If <i>AbbrevNameSize</i> is <b>NULL</b>, this information is not returned.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, at least one of <i>FullNameBuffer</i> or <i>AbbrevNameBuffer</i> was too small for the corresponding name, so the name was truncated.

</td>
</tr>
</table>

## Remarks

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558860">Target Information</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548438">GetSupportedProcessorTypes</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::GetProcessorTypeNamesWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>