---
UID: NF:engextcpp.ExtRemoteData.GetUlongPtr
title: ExtRemoteData::GetUlongPtr method
author: windows-driver-content
description: The GetUlongPtr method returns an unsigned integer version (extended to ULONG64) of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getulongptr.htm
old-project: debugger
ms.assetid: 1a3a870b-9f50-4430-b4f4-6d877d2fac3e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_22ba632d-a45b-40de-b8d7-269c917357d5.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], GetUlongPtr method, ExtRemoteData::GetUlongPtr, GetUlongPtr method [Windows Debugging], GetUlongPtr method [Windows Debugging], ExtRemoteData class, GetUlongPtr,ExtRemoteData.GetUlongPtr, debugger.extremotedata_getulongptr
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
-	ExtRemoteData.GetUlongPtr
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# GetUlongPtr method
The <b>GetUlongPtr</b> method returns an unsigned integer version (extended to ULONG64) of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, which represents the contents of the target's memory. The size of the unsigned integer from the target is the same size as a pointer on the target.

## Syntax

````
ULONG64 GetUlongPtr();
````

## Parameters

This function has no parameters.

## Return Value

<b>GetUlongPtr</b> returns an unsigned integer version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, extended to ULONG64.

## Remarks

The size of the memory represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object must be the same as the size of a pointer on the target, <code>ExtExtension::m_PtrSize</code>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544035">ExtRemoteData::GetLongPtr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544069">ExtRemoteData::GetUlong64</a>



<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544064">ExtRemoteData::GetUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>