---
UID: NF.wdbgexts.ReadPointer
title: ReadPointer function
author: windows-driver-content
description: The ReadPointer function reads a pointer from the target.
old-location: debugger\readpointer.htm
old-project: debugger
ms.assetid: 354b1854-2b3b-4fcf-81cb-fd24595cd9bb
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: ReadPointer
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
req.alt-api: ReadPointer
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

# ReadPointer function



## -description
The <b>ReadPointer</b> function reads a pointer from the target.



## -syntax

````
__inline ULONG ReadPointer(
   ULONG64  Address,
   PULONG64 Pointer
);
````


## -parameters

### -param Address 

Specifies the address of the pointer to read.


### -param Pointer 

Receives the value of the pointer.  If the target uses 32-bit pointers, the pointer is sign-extended to 64 bits.


## -returns
If the function succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.


## -remarks
If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).



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
<a href="debugger.writepointer">WritePointer</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ReadPointer function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

