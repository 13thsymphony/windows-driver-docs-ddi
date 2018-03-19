---
UID: NF:engextcpp.ExtExtension.OnSessionInactive
title: ExtExtension::OnSessionInactive method
author: windows-driver-content
description: The OnSessionInactive method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes inactive.
old-location: debugger\onsessioninactive.htm
old-project: debugger
ms.assetid: 6f9b7636-8808-4783-bba7-70b31ae08238
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_2d9d9c48-9c19-4aa7-b0c5-852643eadcee.xml, ExtExtension, ExtExtension class [Windows Debugging], OnSessionInactive method, ExtExtension::OnSessionInactive, OnSessionInactive method [Windows Debugging], OnSessionInactive method [Windows Debugging], ExtExtension class, OnSessionInactive,ExtExtension.OnSessionInactive, debugger.onsessioninactive
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
-	Engextcpp.hpp
api_name:
-	ExtExtension.OnSessionInactive
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# OnSessionInactive method
The <b>OnSessionInactive</b> method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes inactive.

## Syntax

````
virtual void OnSessionInactive(
  [in] ULONG64 Argument
);
````

## Parameters

`Argument`

Set to zero. (Reserved for future use).


## Return Value

This method does not return a value.

## Remarks

If this method is defined in the extension library class <a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>, it can be used to allow the extension library to cache information about the session without the need to register event callbacks.

This method is called at the end of a session.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>



<a href="..\engextcpp\nf-engextcpp-extextension-onsessionactive.md">OnSessionActive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>