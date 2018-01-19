---
UID : NF:dbgeng.IDebugDataSpaces4.ReadMultiByteStringVirtual
title : IDebugDataSpaces4::ReadMultiByteStringVirtual method
author : windows-driver-content
description : The ReadMultiByteStringVirtual method reads a null-terminated, multibyte string from the target.
old-location : debugger\readmultibytestringvirtual.htm
old-project : debugger
ms.assetid : b86caa13-bdb3-4bc4-b2c1-3e51cbcf396f
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugDataSpaces4, IDebugDataSpaces4::ReadMultiByteStringVirtual, ReadMultiByteStringVirtual
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IDebugDataSpaces4.ReadMultiByteStringVirtual
req.alt-loc : dbgeng.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# ReadMultiByteStringVirtual method
The <b>ReadMultiByteStringVirtual</b> method reads a null-terminated, multibyte string from the target.

## Syntax

````
HRESULT ReadMultiByteStringVirtual(
  [in]            ULONG64 Offset,
  [in]            ULONG   MaxBytes,
  [out, optional] PSTR    Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  StringBytes
);
````

## Parameters

`Offset`

Specifies the location of the string in the process's virtual address space.

`MaxBytes`

Specifies the maximum number of bytes to read from the target.

`Buffer`

Receives the string from the target.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

<div class="alert"><b>Note</b>    The remainder of the buffer, following the returned string, might be overwritten by this method.</div>
<div> </div>

`BufferSize`

Specifies the size, in characters, of the <i>Buffer</i> buffer.

`StringBytes`

Receives the size, in bytes, of the string.  If <i>StringBytes</i> is <b>NULL</b>, this information is not returned.


## Return Value

<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The method was successful.  However <i>Buffer</i> was not large enough to hold the string and the string was truncated to fit in <i>Buffer</i>.  The truncated string is null-terminated if <i>Buffer</i> has space for at least one character.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>A null-terminator was not found after reading <i>MaxBytes</i> from the target.

 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

The engine will read up to <i>MaxBytes</i> from the target looking for a null-terminator.  If the string has more than <i>BufferSize</i> characters, the string will be truncated to fit in <i>Buffer</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554304">ReadMultiByteStringVirtualWide</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554351">ReadUnicodeStringVirtual</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces4::ReadMultiByteStringVirtual method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>