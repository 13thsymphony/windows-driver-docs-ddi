---
UID: NF:engextcpp.ExtRemoteTyped.OutTypeName
title: ExtRemoteTyped::OutTypeName method
author: windows-driver-content
description: The OutTypeName method prints the type name of the typed data represented by this object.
old-location: debugger\extremotetyped_outtypename.htm
old-project: debugger
ms.assetid: fda88a3d-4cdf-4be1-87a7-29e312453686
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_1dd0e308-16ca-4b91-8ad6-7c2d4c7d8da8.xml, ExtRemoteTyped, ExtRemoteTyped interface [Windows Debugging], OutTypeName method, ExtRemoteTyped::OutTypeName, OutTypeName method [Windows Debugging], OutTypeName method [Windows Debugging], ExtRemoteTyped interface, OutTypeName,ExtRemoteTyped.OutTypeName, debugger.extremotetyped_outtypename
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
-	ExtRemoteTyped.OutTypeName
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# OutTypeName method
The <b>OutTypeName</b> method prints the type name of the typed data represented by this object.

## Syntax

````
void OutTypeName();
````

## Parameters

This function has no parameters.

## Return Value

This method does not return a value.

## Remarks

The type name is sent to the debugger engine's output callbacks.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |