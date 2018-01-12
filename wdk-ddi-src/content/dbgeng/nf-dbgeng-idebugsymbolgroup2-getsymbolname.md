---
UID: NF:dbgeng.IDebugSymbolGroup2.GetSymbolName
title: IDebugSymbolGroup2::GetSymbolName method
author: windows-driver-content
description: The GetSymbolName method returns the name of a symbol in a symbol group.
old-location: debugger\getsymbolname.htm
old-project: debugger
ms.assetid: a594e436-3b37-4bba-ba9d-65159fdfb7ac
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbolGroup2, IDebugSymbolGroup2::GetSymbolName, GetSymbolName
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
req.alt-api: IDebugSymbolGroup.GetSymbolName,IDebugSymbolGroup2.GetSymbolName
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

# IDebugSymbolGroup2::GetSymbolName method



## -description
The <b>GetSymbolName</b>  method returns the name of a symbol in a symbol group.



## -syntax

````
HRESULT GetSymbolName(
  [in]            ULONG  Index,
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG NameSize
);
````


## -parameters

### -param Index [in]

The index of the symbol whose name you want.  The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.


### -param Buffer [out, optional]

The symbol name.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

The size of the buffer that <i>Buffer </i>points to.


### -param NameSize [out, optional]

The size of the symbol name.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The method was successful. However, the name of the symbol did not fit in the buffer referred to by the <i>Buffer</i> parameter, so a truncated name was returned.

 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.


## -remarks
For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.


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
<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup::GetSymbolName method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

