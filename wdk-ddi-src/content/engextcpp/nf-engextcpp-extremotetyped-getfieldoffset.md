---
UID: NF:engextcpp.ExtRemoteTyped.GetFieldOffset
title: ExtRemoteTyped::GetFieldOffset method
author: windows-driver-content
description: The GetFieldOffset method returns the offset of a member from the base address of an instance of the type that is represented by this object.
old-location: debugger\extremotetyped_getfieldoffset.htm
old-project: debugger
ms.assetid: d74d5b61-f8e8-4ee0-83d2-cfb003189ef4
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_167b764a-f061-46c2-97ce-71c22ddd9b6f.xml, ExtRemoteTyped, ExtRemoteTyped interface [Windows Debugging], GetFieldOffset method, ExtRemoteTyped::GetFieldOffset, GetFieldOffset method [Windows Debugging], GetFieldOffset method [Windows Debugging], ExtRemoteTyped interface, GetFieldOffset,ExtRemoteTyped.GetFieldOffset, debugger.extremotetyped_getfieldoffset
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
-	ExtRemoteTyped.GetFieldOffset
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# GetFieldOffset method
The <b>GetFieldOffset</b> method returns the offset of a member from the base address of an instance of the type that is represented by this object.

## Syntax

````
ULONG GetFieldOffset(
  [in] PCSTR Field
);
````

## Parameters

`Field`

The name of the member whose offset is requested.  Sub-members can be specified using a dot-separated path (for example, <b>mymember.mysubmember</b>).


## Return Value

<b>GetFieldOffset</b> returns the offset of the member from the base address of an instance of the type.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |

## See Also

<b>IDebugSymbols::GetFieldOffset</b>



<a href="..\wdbgexts\nf-wdbgexts-getfieldoffset.md">GetFieldOffset</a>



<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>