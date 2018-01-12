---
UID: NF:engextcpp.ExtRemoteData.GetLongPtr
title: ExtRemoteData::GetLongPtr method
author: windows-driver-content
description: The GetLongPtr method returns a signed integer version (extended to LONG64) of the ExtRemoteData object, which represents the contents of the target's memory. The size of the unsigned integer from the target is the same size as a pointer on the target.
old-location: debugger\extremotedata_getlongptr.htm
old-project: debugger
ms.assetid: 9f796af1-870b-4349-b86a-3c9d868662f6
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ExtRemoteData, ExtRemoteData::GetLongPtr, GetLongPtr
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
req.alt-api: ExtRemoteData.GetLongPtr
req.alt-loc: engextcpp.hpp
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
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::GetLongPtr method



## -description
The <b>GetLongPtr</b> method returns a signed integer version (extended to LONG64) of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, which represents the contents of the target's memory.  The size of the unsigned integer from the target is the same size as a pointer on the target. 



## -syntax

````
LONG64 GetLongPtr();
````


## -parameters


## -returns
<b>GetLongPtr</b> returns a signed integer version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, extended to LONG64.

<b>GetLongPtr</b> returns a signed integer version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, extended to LONG64.

<b>GetLongPtr</b> returns a signed integer version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, extended to LONG64.


## -remarks
The size of the memory represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object must be the same as the size of a pointer on the target, <code>ExtExtension::m_PtrSize</code>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Engextcpp.hpp (include Engextcpp.hpp)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544030">ExtRemoteData::GetLong</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544033">ExtRemoteData::GetLong64</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544072">ExtRemoteData::GetUlongPtr</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData.GetLongPtr method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

