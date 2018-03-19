---
UID: NF:engextcpp.ExtRemoteData.Read
title: ExtRemoteData::Read method
author: windows-driver-content
description: The Read method reads the contents of the target's memory, represented by the ExtRemoteData object, and then caches the data.
old-location: debugger\extremotedata_read.htm
old-project: debugger
ms.assetid: 3068cbcf-c15b-43e1-bd53-857efea65d83
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_69230a7b-f83c-46fc-88c4-134b506540af.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], Read method, ExtRemoteData::Read, Read method [Windows Debugging], Read method [Windows Debugging], ExtRemoteData class, Read,ExtRemoteData.Read, debugger.extremotedata_read
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
-	ExtRemoteData.Read
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# Read method
The <b>Read</b> method reads the contents of the target's memory, represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, and then caches the data.

## Syntax

````
void Read();
````

## Parameters

This function has no parameters.

## Return Value

This method does not return a value.

## Remarks

When the region of memory is specified either by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544006">ExtRemoteData::ExtRemoteData</a> constructor or by the <a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a> or <a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a> methods, the contents are automatically read from the target and cached.  This method only needs to be called if the memory on the target might have changed.

The data can be retrieved using <a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a> or one of the typed "get" methods.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |

## See Also

<a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544006">ExtRemoteData::ExtRemoteData</a>



<a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a>



<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>