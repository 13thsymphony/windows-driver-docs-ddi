---
UID: NF:engextcpp.ExtExtension.OnSessionAccessible
title: ExtExtension::OnSessionAccessible method
author: windows-driver-content
description: The OnSessionAccessible method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes accessible.
old-location: debugger\onsessionaccessible.htm
old-project: debugger
ms.assetid: 85012fde-fc8b-4728-be5f-6acf502de9bc
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: OnSessionAccessible method [Windows Debugging], ExtExtension, OnSessionAccessible, OnSessionAccessible method [Windows Debugging], ExtExtension class, debugger.onsessionaccessible, ExtExtension::OnSessionAccessible, ExtExtension class [Windows Debugging], OnSessionAccessible method, EngExtCpp_Ref_88df5a39-051b-4d84-840e-8caf5414a0e6.xml
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
-	Engextcpp.hpp
apiname:
-	ExtExtension.OnSessionAccessible
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# OnSessionAccessible method
The <b>OnSessionAccessible</b> method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes accessible.

## Syntax

````
virtual void OnSessionAccessible(
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

This method is called when a target is suspended and, if the session is already accessible, after the extension library is initialized (and <a href="..\engextcpp\nf-engextcpp-extextension-getrawargstr.md">OnSessionActive</a> has been called).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |
| **Library** | engextcpp.hpp |

## See Also

<a href="..\engextcpp\nf-engextcpp-extextension-onsessioninaccessible.md">OnSessionInaccessible</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>

<a href="..\engextcpp\nf-engextcpp-extextension-onsessionactive.md">OnSessionActive</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtExtension.OnSessionAccessible method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>