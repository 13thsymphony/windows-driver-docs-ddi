---
UID: NF:engextcpp.ExtRemoteTyped.operator[]
title: ExtRemoteTyped::operator[] method
author: windows-driver-content
description: The operator[] overloaded operator returns the typed data in the specified array element of the typed data represented by this object.
old-location: debugger\extremotetyped_operatorarray_long.htm
old-project: debugger
ms.assetid: b75a0cec-fda6-45a3-ac60-915fc5862456
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: ExtRemoteTyped, ExtRemoteTyped class [Windows Debugging], operator[] method, ExtRemoteTyped::Operator[], ExtRemoteTyped::operator[], debugger.extremotetyped_operatorarray_long, operator[] method [Windows Debugging], operator[] method [Windows Debugging], ExtRemoteTyped class, operator[],ExtRemoteTyped.operator[]
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
-	ExtRemoteTyped.operator[]
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# ExtRemoteTyped::operator[] method
The <b>operator[]</b> overloaded operator returns the typed data in the specified array element of the typed data represented by this object.

## Syntax

```
ExtRemoteTyped operator[](
  LONG Index
);
```

## Parameters

`Index`

The index of the array element.


## Return Value

The <b>operator[]</b> operator returns a new <b>ExtRemoteTyped</b> object that represents the typed data for the specified element of the array.

## Remarks

If the typed data represented by this object is a pointer and not an array, the pointer is treated like an array.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff544211">ExtRemoteTyped::ArrayElement</a> performs a similar function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544211">ExtRemoteTyped::ArrayElement</a>



<a href="https://msdn.microsoft.com/1c2a78ca-5820-40d5-936a-99d50661c982">ExtRemoteTyped::Operator[] (LONG64)</a>



<a href="https://msdn.microsoft.com/d264f2a1-20fa-4bd3-9db5-f253cc5ad0e6">ExtRemoteTyped::Operator[] (ULONG)</a>



<a href="https://msdn.microsoft.com/60bf48e2-8f44-4ed3-8c35-499e764fcca9">ExtRemoteTyped::Operator[] (ULONG64)</a>