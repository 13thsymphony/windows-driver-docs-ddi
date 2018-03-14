---
UID: NF:engextcpp.ExtRemoteTyped.OutFullValue
title: ExtRemoteTyped::OutFullValue method
author: windows-driver-content
description: The OutFullValue method prints the type and value of the typed data represented by this object.
old-location: debugger\extremotetyped_outfullvalue.htm
old-project: debugger
ms.assetid: 8f5b3e8b-1b01-4a14-b472-cb5de82e869a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_30c4c99e-e68e-4f44-b72c-fa67cdcac0fd.xml, ExtRemoteTyped, ExtRemoteTyped interface [Windows Debugging], OutFullValue method, ExtRemoteTyped::OutFullValue, OutFullValue method [Windows Debugging], OutFullValue method [Windows Debugging], ExtRemoteTyped interface, OutFullValue,ExtRemoteTyped.OutFullValue, debugger.extremotetyped_outfullvalue
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
-	ExtRemoteTyped.OutFullValue
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# OutFullValue method
The <b>OutFullValue</b> method prints the type and value of the typed data represented by this object.

## Syntax

````
void OutFullValue();
````

## Parameters

This function has no parameters.

## Return Value

This method does not return a value.

## Remarks

The <b>OutFullValue</b> method prints more detail than the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544369">ExtRemoteTyped::OutSimpleValue</a> method. For example, <b>OutFullValue</b> prints dereferenced pointers and the values that they point to.

The type and value information is sent to the debugger engine's output callbacks.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544369">ExtRemoteTyped::OutSimpleValue</a>



<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteTyped.OutFullValue method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>