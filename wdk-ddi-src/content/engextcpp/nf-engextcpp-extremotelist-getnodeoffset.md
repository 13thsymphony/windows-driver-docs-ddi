---
UID: NF:engextcpp.ExtRemoteList.GetNodeOffset
title: ExtRemoteList::GetNodeOffset method
author: windows-driver-content
description: The GetNodeOffset method returns the address of the current list item.
old-location: debugger\extremotelist_getnodeoffset.htm
old-project: debugger
ms.assetid: 20c4ec7e-6dc1-4a4f-99d1-bb53213771a5
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_efff4521-d480-48a4-8466-f7db3c052aa1.xml, ExtRemoteList, ExtRemoteList class [Windows Debugging], GetNodeOffset method, ExtRemoteList::GetNodeOffset, GetNodeOffset method [Windows Debugging], GetNodeOffset method [Windows Debugging], ExtRemoteList class, GetNodeOffset,ExtRemoteList.GetNodeOffset, debugger.extremotelist_getnodeoffset
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
-	ExtRemoteList.GetNodeOffset
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# GetNodeOffset method
The <b>GetNodeOffset</b> method returns the address of the current list item.

## Syntax

````
ULONG64 GetNodeOffset();
````

## Parameters

This function has no parameters.

## Return Value

<b>GetNodeOffset</b> returns the location, in the target's memory, of the current item for the current list iteration.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |