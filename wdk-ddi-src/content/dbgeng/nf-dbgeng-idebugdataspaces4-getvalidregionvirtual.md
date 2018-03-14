---
UID: NF:dbgeng.IDebugDataSpaces4.GetValidRegionVirtual
title: IDebugDataSpaces4::GetValidRegionVirtual method
author: windows-driver-content
description: The GetValidRegionVirtual method locates the first valid region of memory in a specified memory range.
old-location: debugger\getvalidregionvirtual.htm
old-project: debugger
ms.assetid: b580c2ef-94f9-4738-bd00-0d5a4753f71a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetValidRegionVirtual method [Windows Debugging], GetValidRegionVirtual method [Windows Debugging], IDebugDataSpaces4 interface, GetValidRegionVirtual,IDebugDataSpaces4.GetValidRegionVirtual, IDebugDataSpaces4, IDebugDataSpaces4 interface [Windows Debugging], GetValidRegionVirtual method, IDebugDataSpaces4::GetValidRegionVirtual, IDebugDataSpaces_594749e6-fa97-49fb-aabe-643ac4415ed9.xml, dbgeng/IDebugDataSpaces4::GetValidRegionVirtual, debugger.getvalidregionvirtual
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
-	IDebugDataSpaces4.GetValidRegionVirtual
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetValidRegionVirtual method
The <b>GetValidRegionVirtual</b> method locates the first valid region of memory in a specified memory range.

## Syntax

````
HRESULT GetValidRegionVirtual(
  [in]  ULONG64  Base,
  [in]  ULONG    Size,
  [out] PULONG64 ValidBase,
  [out] PULONG   ValidSize
);
````

## Parameters

`Base`

Specifies the address of the beginning of the memory range to search for valid memory.

`Size`

Specifies the size, in bytes, of the memory range to search.

`ValidBase`

Receives the address of the beginning of the found valid memory.

`ValidSize`

Receives the size, in bytes, of the valid memory.


## Return Value

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547847">GetNextDifferentlyValidOffsetVirtual</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces4::GetValidRegionVirtual method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>