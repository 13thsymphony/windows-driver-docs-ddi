---
UID: NF:engextcpp.ExtRemoteData.Write
title: ExtRemoteData::Write method
author: windows-driver-content
description: The Write method writes the data cached by the ExtRemoteData object to the region of memory on the target, represented by this object.
old-location: debugger\extremotedata_write.htm
old-project: debugger
ms.assetid: 970c725b-4ea0-42b7-a373-83cb463cd80d
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_1288bed4-2f61-4af4-a226-5157a0622f42.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], Write method, ExtRemoteData::Write, Write method [Windows Debugging], Write method [Windows Debugging], ExtRemoteData class, Write,ExtRemoteData.Write, debugger.extremotedata_write
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
-	ExtRemoteData.Write
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# Write method
The <b>Write</b> method writes the data cached by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object to the region of memory on the target, represented by this object.

## Syntax

````
void Write();
````

## Parameters

This function has no parameters.

## Return Value

This method does not return a value.

## Remarks

This method can be used to reset the region of memory on the target to the currently cached value that was previously read from the target.

It is also possible to directly set the value cached by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, for example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>ExtRemoteData ext_remote_data = new ExtRemoteData(address, sizeof(USHORT));
ext_remote_data.m_Data = (ULONG64) my_ushort;
ext_remote_data.Write();</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |

## See Also

<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544083">ExtRemoteData::Read</a>