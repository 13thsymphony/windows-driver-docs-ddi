---
UID: NF:engextcpp.ExtRemoteData.GetUlong
title: ExtRemoteData::GetUlong method
author: windows-driver-content
description: The GetUlong method returns a ULONG version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getulong.htm
old-project: debugger
ms.assetid: ce25b52e-5ac7-470d-902b-f45350718dff
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: EngExtCpp_Ref_41a112c3-0350-4e54-981c-b5c11697ef2d.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], GetUlong method, ExtRemoteData::GetUlong, GetUlong method [Windows Debugging], GetUlong method [Windows Debugging], ExtRemoteData class, GetUlong,ExtRemoteData.GetUlong, debugger.extremotedata_getulong
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
-	ExtRemoteData.GetUlong
product:
- Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# ExtRemoteData::GetUlong method
The <b>GetUlong</b> method returns a ULONG version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object, which represents the contents of the target's memory.

## Syntax

```
ULONG  throw() GetUlong(

);
```

## Parameters

This function has no parameters.

## Return Value

<b>GetUlong</b> returns the ULONG version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object.

## Remarks

The size of the memory represented by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object must be <code>sizeof(ULONG)</code>.

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