---
UID: NF:engextcpp.ExtRemoteTyped.OutSimpleValue
title: ExtRemoteTyped::OutSimpleValue method
author: windows-driver-content
description: The OutSimpleValue method prints the value of the typed data represented by this object.
old-location: debugger\extremotetyped_outsimplevalue.htm
old-project: debugger
ms.assetid: e9c11c07-bd4a-4d49-a820-4617be691c80
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: EngExtCpp_Ref_8592b96c-7253-42f9-a704-739e539bad66.xml, ExtRemoteTyped, ExtRemoteTyped interface [Windows Debugging], OutSimpleValue method, ExtRemoteTyped::OutSimpleValue, OutSimpleValue method [Windows Debugging], OutSimpleValue method [Windows Debugging], ExtRemoteTyped interface, OutSimpleValue,ExtRemoteTyped.OutSimpleValue, debugger.extremotetyped_outsimplevalue
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	engextcpp.hpp
api_name:
-	ExtRemoteTyped.OutSimpleValue
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# OutSimpleValue method
The <b>OutSimpleValue</b> method prints the value of the typed data represented by this object.

## Syntax

````
void OutSimpleValue();
````

## Parameters

This function has no parameters.

## Return Value

This method does not return a value.

## Remarks

The <b>OutSimpleValue</b> method does not print as much detail as the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544362">ExtRemoteTyped::OutFullValue</a> method.

The value is sent to the debugger engine's output callbacks.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |
| **Library** | engextcpp.hpp |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544362">ExtRemoteTyped::OutFullValue</a>



<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteTyped.OutSimpleValue method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>