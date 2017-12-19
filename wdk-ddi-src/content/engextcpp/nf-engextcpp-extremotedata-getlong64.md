---
UID: NF.engextcpp.ExtRemoteData.GetLong64
title: ExtRemoteData::GetLong64 method
author: windows-driver-content
description: The GetLong64 method returns a LONG64 version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getlong64.htm
old-project: Debugger
ms.assetid: dd6f051a-d287-4cb9-8c53-928415e0f152
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ExtRemoteData, ExtRemoteData::GetLong64, GetLong64
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
req.alt-api: ExtRemoteData.GetLong64
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
---

# ExtRemoteData::GetLong64 method



## -description
The <b>GetLong64</b> method returns a LONG64 version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, which represents the contents of the target's memory.



## -syntax

````
LONG64 GetLong64();
````


## -parameters


## -returns
<b>GetLong64</b> returns the LONG64 version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.

<b>GetLong64</b> returns the LONG64 version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.

<b>GetLong64</b> returns the LONG64 version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.


## -remarks
The size of the memory represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object must be <code>sizeof(LONG64)</code>.


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
<a href="debugger.extremotedata_getdata">ExtRemoteData::GetData</a>
</dt>
<dt>
<a href="debugger.extremotedata_getlong64">ExtRemoteData::GetLong64</a>
</dt>
<dt>
<a href="debugger.extremotedata_getulong">ExtRemoteData::GetUlong</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20ExtRemoteData.GetLong64 method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

