---
UID: NF:engextcpp.ExtRemoteTyped.Set
title: ExtRemoteTyped::Set method
author: windows-driver-content
description: The Set method sets the typed data represented by the ExtRemoteTyped object.
old-location: debugger\extremotetyped_set_bool.htm
old-project: debugger
ms.assetid: e75c17d2-fdf7-4dba-9892-74c764956924
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: ExtRemoteTyped, ExtRemoteTyped class [Windows Debugging], Set method, ExtRemoteTyped::Set, Set method [Windows Debugging], Set method [Windows Debugging], ExtRemoteTyped class, Set,ExtRemoteTyped.Set, debugger.extremotetyped_set_bool
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
-	ExtRemoteTyped.Set
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# ExtRemoteTyped::Set method
The <b>Set</b> method sets the typed data represented by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a> object.

## Syntax

```
void  throw() Set(
  PCSTR Expr
);
```

## Parameters

`Expr`




## Return Value

This method does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a>



<a href="https://msdn.microsoft.com/a19d6aff-c4e4-4188-8f27-3689e91023b4">ExtRemoteTyped::Set (PCSTR)</a>



<a href="https://msdn.microsoft.com/acf789f7-781d-4078-90cc-79b0d2709696">ExtRemoteTyped::Set (PCSTR, ULONG64)</a>



<a href="https://msdn.microsoft.com/fc3d8d9c-0b19-42b3-b4d7-90df4667739b">ExtRemoteTyped::Set (PCSTR, ULONG64, bool)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544384">ExtRemoteTyped::SetPrint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544181">ExtRemoteTypedList</a>