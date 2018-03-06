---
UID: NF:engextcpp.ExtRemoteTyped.GetTypeName
title: ExtRemoteTyped::GetTypeName method
author: windows-driver-content
description: The GetTypeName method returns the type name of the typed data represented by this object.
old-location: debugger\extremotetyped_gettypename.htm
old-project: debugger
ms.assetid: 162b3a05-dccd-4df4-8728-801a8fb39afc
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: EngExtCpp_Ref_063b1f9f-802d-4db4-9661-6f1909d396ee.xml, ExtRemoteTyped, ExtRemoteTyped interface [Windows Debugging], GetTypeName method, ExtRemoteTyped::GetTypeName, GetTypeName method [Windows Debugging], GetTypeName method [Windows Debugging], ExtRemoteTyped interface, GetTypeName,ExtRemoteTyped.GetTypeName, debugger.extremotetyped_gettypename
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
-	ExtRemoteTyped.GetTypeName
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# GetTypeName method
The <b>GetTypeName</b> method returns the type name of the typed data represented by this object.

## Syntax

````
PSTR GetTypeName();
````

## Parameters

This function has no parameters.

## Return Value

<b>GetTypeName</b> returns a string that contains the name of the type.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |
| **Library** | engextcpp.hpp |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544527">EXT_DECLARE_GLOBALS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteTyped.GetTypeName method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>