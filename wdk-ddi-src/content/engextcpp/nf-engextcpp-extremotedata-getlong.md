---
UID: NF:engextcpp.ExtRemoteData.GetLong
title: ExtRemoteData::GetLong method
author: windows-driver-content
description: The GetLong method returns a LONG version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getlong.htm
old-project: debugger
ms.assetid: 064f50e7-bae8-4c29-9802-47efdb749652
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: EngExtCpp_Ref_10a1810d-2e15-490a-baeb-8881106f41a6.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], GetLong method, ExtRemoteData::GetLong, GetLong method [Windows Debugging], GetLong method [Windows Debugging], ExtRemoteData class, GetLong,ExtRemoteData.GetLong, debugger.extremotedata_getlong
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
-	ExtRemoteData.GetLong
product:
- Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# ExtRemoteData::GetLong method
The <b>GetLong</b> method returns a LONG version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object, which represents the contents of the target's memory.

## Syntax

```
LONG  throw() GetLong(

);
```

## Parameters

This function has no parameters.

## Return Value

<b>GetLong</b> returns the LONG version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object.

## Remarks

The size of the memory represented by this <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object must be <code>sizeof(LONG)</code>.

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