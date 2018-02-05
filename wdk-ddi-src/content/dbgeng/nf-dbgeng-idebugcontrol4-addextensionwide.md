---
UID : NF:dbgeng.IDebugControl4.AddExtensionWide
title : IDebugControl4::AddExtensionWide method
author : windows-driver-content
description : The AddExtensionWide method loads an extension library into the debugger engine.
old-location : debugger\addextensionwide.htm
old-project : debugger
ms.assetid : 5c918f44-1ee7-4666-b83a-e13ce02e26db
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : IDebugControl4 interface [Windows Debugging], AddExtensionWide method, AddExtensionWide method [Windows Debugging], AddExtensionWide method [Windows Debugging], IDebugControl4 interface, IDebugControl4::AddExtensionWide, debugger.addextensionwide, IDebugControl4, dbgeng/IDebugControl4::AddExtensionWide, AddExtensionWide
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


# AddExtensionWide method
The <b>AddExtensionWide</b>  method loads an extension library into the <a href="https://msdn.microsoft.com/fa52a1f0-9397-48a5-acbd-ce5347c0baef">debugger engine</a>.

## Syntax

````
HRESULT AddExtensionWide(
  [in]  PCSTR    Path,
  [in]  ULONG    Flags,
  [out] PULONG64 Handle
);
````

## Parameters

`Path`

Specifies the fully qualified path and file name of the extension library to load.

`Flags`

Set to zero.

`Handle`

Receives the handle of the loaded extension library.


## Return Value

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

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

If the extension library has already been loaded, the handle to already loaded library is returned.  The extension library is not loaded again.

The extension library is loaded into the host engine and <i>Path</i> contains a path and file name for this instance of the debugger engine.

For more information on using extension libraries, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539033">Calling Extensions and Extension Functions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546717">GetExtensionByPath</a>

<a href="..\dbgeng\nn-dbgeng-idebugcontrol4.md">IDebugControl4</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554497">RemoveExtension</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugControl4::AddExtensionWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>