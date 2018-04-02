---
UID: NF:engextcpp.ExtRemoteList.Next
title: ExtRemoteList::Next method
author: windows-driver-content
description: The Next method changes the current item to the next item in the list.
old-location: debugger\extremotelist_next.htm
old-project: debugger
ms.assetid: a1bf6f5b-c23d-40ed-b6e2-788066fcf0fc
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: EngExtCpp_Ref_27cc32ed-e2da-4041-8dd7-e2d5a0910c5e.xml, ExtRemoteList, ExtRemoteList class [Windows Debugging], Next method, ExtRemoteList::Next, Next method [Windows Debugging], Next method [Windows Debugging], ExtRemoteList class, Next,ExtRemoteList.Next, debugger.extremotelist_next
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
-	ExtRemoteList.Next
product:
- Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# ExtRemoteList::Next method
The <b>Next</b> method changes the current item to the next item in the list.

## Syntax

```
void Next(

);
```

## Parameters

This function has no parameters.

## Return Value

This method does not return a value.

## Remarks

If <b>Next</b> reaches the end of the list, subsequent calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff544136">ExtRemoteList::HasNode</a> will return <code>false</code>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544114">ExtRemoteList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544136">ExtRemoteList::HasNode</a>