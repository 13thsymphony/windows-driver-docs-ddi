---
UID: NF:engextcpp.ExtRemoteData.ReadBuffer
title: ExtRemoteData::ReadBuffer method
author: windows-driver-content
description: The ReadBuffer method reads data from the target's memory. The data is located in the beginning of the region represented by the ExtRemoteData object. However, the size of the data can be different.
old-location: debugger\extremotedata_readbuffer.htm
old-project: debugger
ms.assetid: 1ad13196-a133-4168-9a36-1f7e4ed5c4f1
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_b27c97d0-4083-4773-b323-55f915dfdd05.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], ReadBuffer method, ExtRemoteData::ReadBuffer, ReadBuffer method [Windows Debugging], ReadBuffer method [Windows Debugging], ExtRemoteData class, ReadBuffer,ExtRemoteData.ReadBuffer, debugger.extremotedata_readbuffer
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
-	ExtRemoteData.ReadBuffer
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---


# ReadBuffer method
The <b>ReadBuffer</b> method reads data from the target's memory.  The data is located in the beginning of the region represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.  However, the size of the data can be different.

## Syntax

````
ULONG ReadBuffer(
  [out] PVOID Buffer,
  [in]  ULONG Bytes,
  [in]  bool  MustReadAll
);
````

## Parameters

`Buffer`

Pointer that receives the data read from the target.

`Bytes`

Specifies the number of bytes to read.  The <i>Buffer</i> buffer must be at least this size.

`MustReadAll`

Specifies what happens if the debugger engine is unable to read all the data from the target.  If <i>MustReadAll</i> is <code>true</code> and the debugger engine is unable to read <i>Bytes</i> bytes from the target, an <b>ExtRemoteException</b> will be thrown.  If <i>MustReadAll</i>  is <code>false</code>, no exception will be thrown if the engine is unable to read the requested number of bytes from the target.


## Return Value

<b>ReadBuffer</b> returns the number of bytes read from the target and copied into the <i>Buffer</i> buffer.  If <i>MustReadAll</i> is <code>true</code>, the value of <i>Bytes</i> will be returned (unless an exception is thrown).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |

## See Also

<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544110">ExtRemoteData::WriteBuffer</a>