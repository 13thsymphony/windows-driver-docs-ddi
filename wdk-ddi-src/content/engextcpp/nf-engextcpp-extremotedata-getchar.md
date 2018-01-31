---
UID : NF:engextcpp.ExtRemoteData.GetChar
title : ExtRemoteData::GetChar method
author : windows-driver-content
description : The GetChar method returns a CHAR version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location : debugger\extremotedata_getchar.htm
old-project : debugger
ms.assetid : bf916e7c-f03b-4d02-8260-bc90e8957cc9
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : ExtRemoteData class [Windows Debugging], GetChar method, EngExtCpp_Ref_98ced053-a952-4c9f-af2b-0aab9d20e311.xml, ExtRemoteData::GetChar, ExtRemoteData, GetChar, GetChar method [Windows Debugging], ExtRemoteData class, GetChar method [Windows Debugging], debugger.extremotedata_getchar
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : engextcpp.hpp
req.include-header : Engextcpp.hpp
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : engextcpp.hpp
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSILO_DRIVER_CAPABILITIES, SILO_DRIVER_CAPABILITIES"
---


# GetChar method
The <b>GetChar</b> method returns a CHAR version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, which represents the contents of the target's memory.

## Syntax

````
CHAR GetChar();
````

## Parameters

This function has no parameters.

## Return Value

<b>GetChar</b> returns the CHAR version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.

## Remarks

The size of the memory represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object must be <code>sizeof(CHAR)</code>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>

<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544057">ExtRemoteData::GetUchar</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData.GetChar method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>