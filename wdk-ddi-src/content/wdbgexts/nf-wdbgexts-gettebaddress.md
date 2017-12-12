---
UID: NF.wdbgexts.GetTebAddress
title: GetTebAddress function
author: windows-driver-content
description: The GetTebAddress function returns the address of the thread environment block (TEB) for the current operating system thread.
old-location: debugger\gettebaddress.htm
old-project: debugger
ms.assetid: 6dbe7da6-31f6-43f2-aa25-be6f13c8d8d8
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: GetTebAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetTebAddress
req.alt-loc: wdbgexts.h
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
req.product: Windows 10 or later.
---

# GetTebAddress function



## -description
The <b>GetTebAddress</b> function returns the address of the thread environment block (TEB) for the current operating system thread.



## -syntax

````
__inline VOID GetTebAddress(
   PULONGLONG Address
);
````


## -parameters

### -param Address 

Receives the address of the TEB for the current operating system thread.


## -returns
None


## -remarks
In user-mode debugging, the TEB for the current thread is returned.  In kernel-mode debugging, the TEB for the operating system thread that was running on the current processor when the last event occurred is returned.


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
<dt>Wdbgexts.h (include Wdbgexts.h or Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="debugger.getpebaddress">GetPebAddress</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20GetTebAddress function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

