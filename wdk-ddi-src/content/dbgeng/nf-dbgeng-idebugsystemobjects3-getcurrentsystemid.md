---
UID: NF:dbgeng.IDebugSystemObjects3.GetCurrentSystemId
title: IDebugSystemObjects3::GetCurrentSystemId method
author: windows-driver-content
description: The GetCurrentSystemId method returns the engine target ID for the current process.
old-location: debugger\getcurrentsystemid.htm
old-project: debugger
ms.assetid: 2ff5091b-7cf8-4972-b87b-b18d25bb23e9
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetCurrentSystemId method [Windows Debugging], dbgeng/IDebugSystemObjects4::GetCurrentSystemId, IDebugSystemObjects3, GetCurrentSystemId, debugger.getcurrentsystemid, dbgeng/IDebugSystemObjects3::GetCurrentSystemId, IDebugSystemObjects4::GetCurrentSystemId, IDebugSystemObjects3 interface [Windows Debugging], GetCurrentSystemId method, GetCurrentSystemId method [Windows Debugging], IDebugSystemObjects3 interface, GetCurrentSystemId method [Windows Debugging], IDebugSystemObjects4 interface, IDebugSystemObjects_02c8ff30-b552-465a-9be3-4e0526e1d6e1.xml, IDebugSystemObjects4 interface [Windows Debugging], GetCurrentSystemId method, IDebugSystemObjects3::GetCurrentSystemId
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugSystemObjects3.GetCurrentSystemId
-	IDebugSystemObjects4.GetCurrentSystemId
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetCurrentSystemId method
The <b>GetCurrentSystemId</b> method returns the engine target ID for the current process.

## Syntax

````
HRESULT GetCurrentSystemId(
  [out] PULONG Id
);
````

## Parameters

`Id`

Receives the engine target ID.


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


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects4.md">IDebugSystemObjects4</a>



<a href="..\dbgeng\nn-dbgeng-idebugsystemobjects3.md">IDebugSystemObjects3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541386">Debugging Session and Execution Model</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSystemObjects3::GetCurrentSystemId method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>