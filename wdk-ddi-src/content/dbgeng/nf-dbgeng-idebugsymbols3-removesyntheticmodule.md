---
UID: NF:dbgeng.IDebugSymbols3.RemoveSyntheticModule
title: IDebugSymbols3::RemoveSyntheticModule method
author: windows-driver-content
description: The RemoveSyntheticModule method removes a synthetic module from the module list the debugger maintains for the current process.
old-location: debugger\removesyntheticmodule.htm
old-project: debugger
ms.assetid: 951b42b6-4d6a-45af-a27f-6e8056676bb0
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3::RemoveSyntheticModule, RemoveSyntheticModule
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
req.alt-api: IDebugSymbols3.RemoveSyntheticModule
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

# IDebugSymbols3::RemoveSyntheticModule method



## -description
The <b>RemoveSyntheticModule</b> method removes a synthetic module from the module list the debugger maintains for the current process.



## -syntax

````
HRESULT RemoveSyntheticModule(
  [in] ULONG64 Base
);
````


## -parameters

### -param Base [in]

Specifies the location in the process's virtual address space of the base of the synthetic module.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>No synthetic module was found at the specified location.  This is returned if a synthetic module at this location was previously removed or discarded.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
If all the modules are reloaded - for example, by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554379">Reload</a> with the  <i>Module</i> parameter set to the empty string - all synthetic modules will be discarded.

For more information about synthetic modules, see Synthetic Modules.


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
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537937">AddSyntheticModule</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554542">RemoveSyntheticSymbol</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::RemoveSyntheticModule method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

