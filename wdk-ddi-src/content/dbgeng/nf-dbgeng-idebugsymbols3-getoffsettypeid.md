---
UID: NF.dbgeng.IDebugSymbols3.GetOffsetTypeId
title: IDebugSymbols3::GetOffsetTypeId method
author: windows-driver-content
description: The GetOffsetTypeId method returns the type ID of the symbol closest to the specified memory location.
old-location: debugger\getoffsettypeid.htm
old-project: Debugger
ms.assetid: cf533f21-90eb-46ec-860f-d12a8d40c430
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IDebugSymbols3, IDebugSymbols3::GetOffsetTypeId, GetOffsetTypeId
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
req.alt-api: IDebugSymbols.GetOffsetTypeId,IDebugSymbols2.GetOffsetTypeId,IDebugSymbols3.GetOffsetTypeId
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

# IDebugSymbols3::GetOffsetTypeId method



## -description
The <b>GetOffsetTypeId</b> method returns the type ID of the symbol closest to the specified memory location.



## -syntax

````
HRESULT GetOffsetTypeId(
  [in]            ULONG64  Offset,
  [out]           PULONG   TypeId,
  [out, optional] PULONG64 Module
);
````


## -parameters

### -param Offset [in]

Specifies the location in the target's memory for the symbol.  The symbol closest to this location is used.


### -param TypeId [out]

Receives the type ID of the symbol.


### -param Module [out, optional]

Specifies the location in the target's memory address space of the base of the module to which the symbol belongs.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.  If <i>Module</i> is <b>NULL</b>, this information is not returned.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful

 


## -remarks
For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.


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
<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="debugger.gettypeid">GetTypeId</a>
</dt>
<dt>
<a href="debugger.getsymboltypeid">GetSymbolTypeId</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugSymbols::GetOffsetTypeId method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

