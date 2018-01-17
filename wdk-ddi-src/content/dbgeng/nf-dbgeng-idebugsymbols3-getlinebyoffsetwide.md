---
UID: NF:dbgeng.IDebugSymbols3.GetLineByOffsetWide
title: IDebugSymbols3::GetLineByOffsetWide method
author: windows-driver-content
description: The GetLineByOffsetWide method returns the source filename and the line number within the source file of an instruction in the target.
old-location: debugger\getlinebyoffsetwide.htm
old-project: debugger
ms.assetid: e780be4b-ac62-43c2-9767-7745ff1c7dbb
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3::GetLineByOffsetWide, GetLineByOffsetWide
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
req.alt-api: IDebugSymbols3.GetLineByOffsetWide
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
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetLineByOffsetWide method



## -description
The <b>GetLineByOffsetWide</b>  method returns the source filename and the line number within the source file of an instruction in the target.



## -syntax

````
HRESULT GetLineByOffsetWide(
  [in]            ULONG64  Offset,
  [out, optional] PULONG   Line,
  [out, optional] PWSTR    FileBuffer,
  [in]            ULONG    FileBufferSize,
  [out, optional] PULONG   FileSize,
  [out, optional] PULONG64 Displacement
);
````


## -parameters

### -param Offset [in]

Specifies the location in the target's virtual address space of the instruction for which to return the source file and line number.


### -param Line [out, optional]

Receives the line number within the source file of the instruction specified by <i>Offset</i>.  If <i>Line</i> is <b>NULL</b>, this information is not returned.


### -param FileBuffer [out, optional]

Receives the file name of the file that contains the instruction specified by <i>Offset</i>.  If <i>FileBuffer</i> is <b>NULL</b>, this information is not returned.


### -param FileBufferSize [in]

Specifies the size, in characters, of the <i>FileBuffer</i> buffer.


### -param FileSize [out, optional]

Specifies the size, in characters, of the source filename.  If <i>FileSize</i> is <b>NULL</b>, this information is not returned.


### -param Displacement [out, optional]

Receives the difference between the location specified in <i>Offset</i> and the location of the first instruction of the returned line.  If <i>Displacement</i> is <b>NULL</b>, this information is not returned.


## -returns
This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The method was successful. However, the buffer was not large enough to hold the name of the source file and the name was truncated.

 


## -remarks
For more information about source files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560141">Using Source Files</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548022">GetOffsetByLine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetLineByOffsetWide method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

