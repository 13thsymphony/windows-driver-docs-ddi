---
UID: NF:dbgeng.IDebugDataSpaces4.FillPhysical
title: IDebugDataSpaces4::FillPhysical method
author: windows-driver-content
description: The FillPhysical method writes a pattern of bytes to the target's physical memory. The pattern is written repeatedly until the specified memory range is filled.
old-location: debugger\fillphysical.htm
old-project: debugger
ms.assetid: 9fd2cc6d-c891-4566-896b-80d56d143e8d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4::FillPhysical, FillPhysical
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugDataSpaces2.FillPhysical,IDebugDataSpaces3.FillPhysical,IDebugDataSpaces4.FillPhysical
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugDataSpaces4::FillPhysical method



## -description
The <b>FillPhysical</b> method writes a pattern of bytes to the target's physical memory.  The pattern is written repeatedly until the specified memory range is filled.



## -syntax

````
HRESULT FillPhysical(
  [in]            ULONG64 Start,
  [in]            ULONG   Size,
  [in]            PVOID   Pattern,
  [in]            ULONG   PatternSize,
  [out, optional] PULONG  Filled
);
````


## -parameters

### -param Start [in]

Specifies the location in the target's physical memory at which to start writing the pattern.


### -param Size [in]

Specifies how many bytes to write to the target's memory.


### -param Pattern [in]

Specifies the pattern to write.


### -param PatternSize [in]

Specifies the size in bytes of the pattern.


### -param Filled [out, optional]

Receives the number of bytes written.  If it is set to <b>NULL</b>, this information isn't returned.


## -returns
This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
This method writes the pattern to the target's memory as many times as will fit in <i>Size</i> bytes.

If the final copy of the pattern will not completely fit into the memory range, it will only be partially written.  This includes the case where the size of the pattern is larger than the value of <i>Size</i>, and the extra bytes in the pattern are ignored.


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
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces2.md">IDebugDataSpaces2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561432">WritePhysical</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces2::FillPhysical method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

