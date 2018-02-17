---
UID: NF:engextcpp.ExtRemoteData.ReadBuffer
title: ExtRemoteData::ReadBuffer method
author: windows-driver-content
description: The ReadBuffer method reads data from the target's memory. The data is located in the beginning of the region represented by the ExtRemoteData object. However, the size of the data can be different.
old-location: debugger\extremotedata_readbuffer.htm
old-project: debugger
ms.assetid: 1ad13196-a133-4168-9a36-1f7e4ed5c4f1
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.extremotedata_readbuffer, ReadBuffer method [Windows Debugging], ExtRemoteData, ExtRemoteData::ReadBuffer, EngExtCpp_Ref_b27c97d0-4083-4773-b323-55f915dfdd05.xml, ReadBuffer method [Windows Debugging], ExtRemoteData class, ReadBuffer, ExtRemoteData class [Windows Debugging], ReadBuffer method
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
-	engextcpp.hpp
apiname:
-	ExtRemoteData.ReadBuffer
product: Windows
targetos: Windows
req.typenames: "*PSILO_DRIVER_CAPABILITIES, SILO_DRIVER_CAPABILITIES"
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
| **Library** | engextcpp.hpp |

## See Also

<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544110">ExtRemoteData::WriteBuffer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData.ReadBuffer method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>