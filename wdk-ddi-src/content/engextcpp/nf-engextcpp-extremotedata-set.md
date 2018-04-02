---
UID: NF:engextcpp.ExtRemoteData.Set
title: ExtRemoteData::Set method
author: windows-driver-content
description: The Set method sets the region of the target's memory represented by the ExtRemoteData object.
old-location: debugger\extremotedata_set_offset_bytes.htm
old-project: debugger
ms.assetid: 50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: ExtRemoteData, ExtRemoteData interface [Windows Debugging], Set method, ExtRemoteData::Set, Set method [Windows Debugging], Set method [Windows Debugging], ExtRemoteData interface, Set,ExtRemoteData.Set, debugger.extremotedata_set_offset_bytes, engextcpp/ExtRemoteData::Set
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
-	engextcpp.hpp
api_name:
-	ExtRemoteData.Set
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# ExtRemoteData::Set method
The <b>Set</b> method sets the region of the target's memory represented by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object.

## Syntax

```
void  throw() Set(
  ULONG64 Offset,
  ULONG   Bytes
);
```

## Parameters

`Offset`

Location of the beginning of the memory region in the target's virtual address space.

`Bytes`

Number of bytes in the memory region.


## Return Value

This method does not return a value.

## Remarks

The <b>Set</b> method will read the contents of the specified region of memory and cache the data.  The data can be retrieved using <a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a> or one of the ExtRemoteTyped::Get<i>Xxx</i> methods.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544006">ExtRemoteData::ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>



<a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set (Typed)</a>