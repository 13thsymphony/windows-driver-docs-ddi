---
UID: NF:engextcpp.ExtRemoteData.GetLong64
title: ExtRemoteData::GetLong64 method
author: windows-driver-content
description: The GetLong64 method returns a LONG64 version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getlong64.htm
old-project: debugger
ms.assetid: dd6f051a-d287-4cb9-8c53-928415e0f152
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: EngExtCpp_Ref_4b2bf03d-7a55-4cee-826b-2b384972392f.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], GetLong64 method, ExtRemoteData::GetLong64, GetLong64 method [Windows Debugging], GetLong64 method [Windows Debugging], ExtRemoteData class, GetLong64,ExtRemoteData.GetLong64, debugger.extremotedata_getlong64
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
-	ExtRemoteData.GetLong64
product:
- Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# ExtRemoteData::GetLong64 method
The <b>GetLong64</b> method returns a LONG64 version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object, which represents the contents of the target's memory.

## Syntax

```
LONG64  throw() GetLong64(

);
```

## Parameters

This function has no parameters.

## Return Value

<b>GetLong64</b> returns the LONG64 version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object.

## Remarks

The size of the memory represented by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object must be <code>sizeof(LONG64)</code>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544033">ExtRemoteData::GetLong64</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544064">ExtRemoteData::GetUlong</a>