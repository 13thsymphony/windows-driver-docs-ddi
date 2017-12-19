---
UID: NF.dbgeng.IDebugDataSpaces4.ReadUnicodeStringVirtualWide
title: IDebugDataSpaces4::ReadUnicodeStringVirtualWide method
author: windows-driver-content
description: The ReadUnicodeStringVirtualWide method reads a null-terminated, Unicode string from the target.
old-location: debugger\readunicodestringvirtualwide.htm
old-project: Debugger
ms.assetid: 7c360f9a-83f6-4bc8-abb4-08d1b0c4fdc9
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces4::ReadUnicodeStringVirtualWide, ReadUnicodeStringVirtualWide
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
req.alt-api: IDebugDataSpaces4.ReadUnicodeStringVirtualWide
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
---

# IDebugDataSpaces4::ReadUnicodeStringVirtualWide method



## -description
The <b>ReadUnicodeStringVirtualWide</b> method reads a null-terminated, Unicode string from the target.



## -syntax

````
HRESULT ReadUnicodeStringVirtualWide(
  [in]            ULONG64 Offset,
  [in]            ULONG   MaxBytes,
  [out, optional] PWSTR   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  StringBytes
);
````


## -parameters

### -param Offset [in]

Specifies the location of the string in the process's virtual address space.


### -param MaxBytes [in]

Specifies the maximum number of bytes to read from the target.


### -param Buffer [out, optional]

Receives the string from the target.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

<div class="alert"><b>Note</b>    The remainder of the buffer, following the returned string, might be overwritten by this method.</div>
<div> </div>

### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param StringBytes [out, optional]

Receives the size, in bytes, of the string.  If <i>StringBytes</i> is <b>NULL</b>, this information is not returned.


## -returns
This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl><dl>
<dt><b>S_FALSE</b></dt>
</dl>The method was successful.  However <i>Buffer</i> was not large enough to hold the string and the string was truncated to fit in <i>Buffer</i>.  The truncated string is null-terminated if <i>Buffer</i> has space for at least one character.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>A null-terminator was not found after reading <i>MaxBytes</i> from the target.

 

The method was successful.


## -remarks
The engine will read up to <i>MaxBytes</i> from the target, looking for a null-terminator.  If the string has more than <i>BufferSize</i> characters, the string will be truncated to fit in <i>Buffer</i>.


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
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>
</dt>
<dt>
<a href="debugger.readmultibytestringvirtualwide">ReadMultiByteStringVirtualWide</a>
</dt>
<dt>
<a href="debugger.readunicodestringvirtual">ReadUnicodeStringVirtual</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugDataSpaces4::ReadUnicodeStringVirtualWide method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

