---
UID: NF:engextcpp.ExtRemoteData.GetUlong64
title: ExtRemoteData::GetUlong64 method
author: windows-driver-content
description: The GetUlong64 method returns a ULONG64 version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getulong64.htm
old-project: debugger
ms.assetid: f88694a0-aa76-434a-b436-3c0b6903cad6
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: EngExtCpp_Ref_8310177e-7943-4f2c-92bd-b69848c9e9f0.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], GetUlong64 method, ExtRemoteData::GetUlong64, GetUlong64 method [Windows Debugging], GetUlong64 method [Windows Debugging], ExtRemoteData class, GetUlong64,ExtRemoteData.GetUlong64, debugger.extremotedata_getulong64
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
-	ExtRemoteData.GetUlong64
product:
- Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# ExtRemoteData::GetUlong64 method
The <b>GetUlong64</b> method returns a ULONG64 version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object, which represents the contents of the target's memory.

## Syntax

```
ULONG64  throw() GetUlong64(

);
```

## Parameters

This function has no parameters.

## Return Value

<b>GetUlong64</b> returns the ULONG64 version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object.

## Remarks

The size of the memory represented by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object must be <code>sizeof(ULONG64)</code>.

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