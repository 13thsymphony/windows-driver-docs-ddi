---
UID: NF.engextcpp.ExtRemoteTyped.GetFieldOffset
title: ExtRemoteTyped::GetFieldOffset method
author: windows-driver-content
description: The GetFieldOffset method returns the offset of a member from the base address of an instance of the type that is represented by this object.
old-location: debugger\extremotetyped_getfieldoffset.htm
old-project: Debugger
ms.assetid: d74d5b61-f8e8-4ee0-83d2-cfb003189ef4
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ExtRemoteTyped, ExtRemoteTyped::GetFieldOffset, GetFieldOffset
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
req.alt-api: ExtRemoteTyped.GetFieldOffset
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

# ExtRemoteTyped::GetFieldOffset method



## -description
The <b>GetFieldOffset</b> method returns the offset of a member from the base address of an instance of the type that is represented by this object.



## -syntax

````
ULONG GetFieldOffset(
  [in] PCSTR Field
);
````


## -parameters

### -param Field [in]

The name of the member whose offset is requested.  Sub-members can be specified using a dot-separated path (for example, <b>mymember.mysubmember</b>).


## -returns
<b>GetFieldOffset</b> returns the offset of the member from the base address of an instance of the type.


## -remarks


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
<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>
</dt>
<dt>
<a href="debugger.getfieldoffset">GetFieldOffset</a>
</dt>
<dt><b>IDebugSymbols::GetFieldOffset</b></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20ExtRemoteTyped.GetFieldOffset method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

