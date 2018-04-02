---
UID: NF:engextcpp.ExtRemoteTyped.Copy
title: ExtRemoteTyped::Copy method
author: windows-driver-content
description: The Copy method sets the typed data represented by the ExtRemoteTyped object by copying the information from another object.
old-location: debugger\extremotetyped_copy_debug_typed_data.htm
old-project: debugger
ms.assetid: bfeafa09-49b7-45b3-84d8-afad5f43b78e
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: Copy method [Windows Debugging], Copy method [Windows Debugging], ExtRemoteTyped class, Copy,ExtRemoteTyped.Copy, ExtRemoteTyped, ExtRemoteTyped class [Windows Debugging], Copy method, ExtRemoteTyped::Copy, debugger.extremotetyped_copy_debug_typed_data
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
-	ExtRemoteTyped.Copy
product:
- Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# ExtRemoteTyped::Copy method
The <b>Copy</b> method sets the typed data represented by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a> object by copying the information from another object.

## Syntax

```
void  throw() Copy(
  const DEBUG_TYPED_DATA *Typed
);
```

## Parameters

`Typed`

The typed data description to copy. This becomes the typed data represented by this object.


## Return Value

This method does not return a value.

## Remarks

The typed data can also be copied using the <a href="https://msdn.microsoft.com/7cc91411-3332-4a33-8873-832f71fd3281">ExtRemoteTyped::Copy ExtRemoteTyped</a> method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541706">DEBUG_TYPED_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a>



<a href="https://msdn.microsoft.com/f7a63a6a-24fa-4c93-ac2e-c44f7984a2c8">ExtRemoteTyped::operator=</a>