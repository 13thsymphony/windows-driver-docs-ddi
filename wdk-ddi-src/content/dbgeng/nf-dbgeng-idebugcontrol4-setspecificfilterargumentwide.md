---
UID : NF:dbgeng.IDebugControl4.SetSpecificFilterArgumentWide
title : IDebugControl4::SetSpecificFilterArgumentWide method
author : windows-driver-content
description : The SetSpecificFilterArgumentWide method sets the value of filter argument for the specific filters that can have an argument.
old-location : debugger\setspecificfilterargumentwide.htm
old-project : debugger
ms.assetid : 416c4de2-f200-491a-a319-fb0a4fd86f86
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : debugger.setspecificfilterargumentwide, SetSpecificFilterArgumentWide, dbgeng/IDebugControl4::SetSpecificFilterArgumentWide, SetSpecificFilterArgumentWide method [Windows Debugging], IDebugControl4 interface, IDebugControl4, IDebugControl4::SetSpecificFilterArgumentWide, IDebugControl4 interface [Windows Debugging], SetSpecificFilterArgumentWide method, SetSpecificFilterArgumentWide method [Windows Debugging]
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
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# SetSpecificFilterArgumentWide method
The <b>SetSpecificFilterArgumentWide</b>  method sets the value of filter argument for the specific filters that can have an argument.

## Syntax

````
HRESULT SetSpecificFilterArgumentWide(
  [in] ULONG  Index,
  [in] PCWSTR Argument
);
````

## Parameters

`Index`

Specifies the index of the specific filter whose argument will be set.  <i>Index</i> must be the index of a specific filter that has an argument.

`Argument`

Specifies the argument for the specific filter.  The interpretation of this argument depends on the specific filter.


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
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
<i>Index</i> does not refer to a specific filter that has an argument.

</td>
</tr>
</table>

## Remarks

For a list of specific filters that have argument and the interpretation of those arguments, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543071">Event Filters</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548386">GetSpecificFilterArgument</a>

<a href="https://msdn.microsoft.com/fdb5059f-e7d9-4e14-aa3d-030e72c30732">sx, sxd, sxe, sxi, sxn (Set Exceptions)</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::SetSpecificFilterArgumentWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>