---
UID: NF:engextcpp.ExtRemoteTyped.GetTypeSize
title: ExtRemoteTyped::GetTypeSize method
author: windows-driver-content
description: The GetTypeSize method returns the size of the type represented by this object.
old-location: debugger\extremotetyped_gettypesize.htm
old-project: debugger
ms.assetid: 0b681f00-6cec-4598-abee-e9a97bd53582
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: EngExtCpp_Ref_a0708ab0-c6c3-441a-958d-7f26fad32869.xml, ExtRemoteTyped, ExtRemoteTyped interface [Windows Debugging], GetTypeSize method, ExtRemoteTyped::GetTypeSize, GetTypeSize method [Windows Debugging], GetTypeSize method [Windows Debugging], ExtRemoteTyped interface, GetTypeSize,ExtRemoteTyped.GetTypeSize, debugger.extremotetyped_gettypesize
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
-	ExtRemoteTyped.GetTypeSize
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# GetTypeSize method
The <b>GetTypeSize</b> method returns the size of the type represented by this object.

## Syntax

````
ULONG GetTypeSize();
````

## Parameters

This function has no parameters.

## Return Value

<b>GetTypeSize</b> returns the size, in bytes, of instance of the type.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |
| **Library** | engextcpp.hpp |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549457">GetTypeSize</a>



<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteTyped.GetTypeSize method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>