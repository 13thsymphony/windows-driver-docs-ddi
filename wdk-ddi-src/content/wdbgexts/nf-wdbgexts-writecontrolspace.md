---
UID: NF:wdbgexts.WriteControlSpace
title: WriteControlSpace function
author: windows-driver-content
description: The WriteControlSpace function writes to the processor-specific control space of the current target.
old-location: debugger\writecontrolspace.htm
old-project: debugger
ms.assetid: 12ea119e-9d56-4a1d-a8c6-3999147dfaac
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: WriteControlSpace
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
req.alt-api: WriteControlSpace
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
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# WriteControlSpace function



## -description
The <b>WriteControlSpace</b> function writes to the processor-specific control space of the current target.



## -syntax

````
VOID WriteControlSpace(
   USHORT processor,
   ULONG  address,
   PVOID  buf,
   ULONG  size
);
````


## -parameters

### -param processor 

Specifies the index of the processor whose control space is to be written.


### -param address 

Specifies the address of the control space.


### -param buf 

Specifies the data to be written to the control space.


### -param size 

Specifies the number of bytes to be written.  This is the number of bytes in the <i>buf</i> buffer.


## -returns
None


## -remarks
This function can only be called in kernel-mode debugging.


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
<a href="..\wdbgexts\ns-wdbgexts-_readcontrolspace.md">ReadControlSpace</a>
</dt>
<dt>
<a href="..\wdbgexts\ns-wdbgexts-_readcontrolspace64.md">ReadControlSpace64</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20WriteControlSpace function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

