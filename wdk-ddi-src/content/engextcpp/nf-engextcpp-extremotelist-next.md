---
UID: NF:engextcpp.ExtRemoteList.Next
title: ExtRemoteList::Next method
author: windows-driver-content
description: The Next method changes the current item to the next item in the list.
old-location: debugger\extremotelist_next.htm
old-project: debugger
ms.assetid: a1bf6f5b-c23d-40ed-b6e2-788066fcf0fc
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: Next method [Windows Debugging], ExtRemoteList class, Next, debugger.extremotelist_next, ExtRemoteList::Next, Next method [Windows Debugging], ExtRemoteList, EngExtCpp_Ref_27cc32ed-e2da-4041-8dd7-e2d5a0910c5e.xml, ExtRemoteList class [Windows Debugging], Next method
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
req.lib: engextcpp.hpp
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	engextcpp.hpp
apiname:
-	ExtRemoteList.Next
product: Windows
targetos: Windows
req.typenames: "*PSILO_DRIVER_CAPABILITIES, SILO_DRIVER_CAPABILITIES"
---


# Next method
The <b>Next</b> method changes the current item to the next item in the list.

## Syntax

````
void Next();
````

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
| **Library** | engextcpp.hpp |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544136">ExtRemoteList::HasNode</a>



<a href="..\engextcpp\nl-engextcpp-extremotelist.md">ExtRemoteList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteList.Next method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>