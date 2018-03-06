---
UID: NF:dbgeng.IDebugSymbols3.AddSyntheticModule
title: IDebugSymbols3::AddSyntheticModule method
author: windows-driver-content
description: The AddSyntheticModule method adds a synthetic module to the module list the debugger maintains for the current process.
old-location: debugger\addsyntheticmodule.htm
old-project: debugger
ms.assetid: 87d9f307-996b-47df-b3dd-368fef6c1042
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AddSyntheticModule method [Windows Debugging], AddSyntheticModule method [Windows Debugging], IDebugSymbols3 interface, AddSyntheticModule,IDebugSymbols3.AddSyntheticModule, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], AddSyntheticModule method, IDebugSymbols3::AddSyntheticModule, IDebugSymbols_ecccfdc4-2942-480c-9f78-c21c4ed46c90.xml, dbgeng/IDebugSymbols3::AddSyntheticModule, debugger.addsyntheticmodule
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: dbgeng.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Dbgeng.h
api_name:
-	IDebugSymbols3.AddSyntheticModule
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# AddSyntheticModule method
The <b>AddSyntheticModule</b>  method adds a synthetic module to the module list the debugger maintains for the <a href="https://msdn.microsoft.com/295b05a3-e27f-4761-a562-7e87e25bfd3b">current process</a>.

## Syntax

````
HRESULT AddSyntheticModule(
  [in] ULONG64 Base,
  [in] ULONG   Size,
  [in] PCSTR   ImagePath,
  [in] PCSTR   ModuleName,
  [in] ULONG   Flags
);
````

## Parameters

`Base`

Specifies the location in the process's virtual address space of the base of the synthetic module.

`Size`

Specifies the size in bytes of the synthetic module.

`ImagePath`

Specifies the image name of the synthetic module.  This is the name that will be returned as the name of the executable file for the synthetic module.  The full path should be included if known.

`ModuleName`

Specifies the module name for the synthetic module.

`Flags`

Set to DEBUG_ADDSYNTHMOD_DEFAULT.


## Return Value

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

The memory region of the synthetic module, described by the <i>Base</i> and <i>Size</i> parameters, must not overlap the memory region of any other module.

If all the modules are reloaded - for example, by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554379">Reload</a> with the  <i>Module</i> parameter set to an empty string - all synthetic modules will be discarded.

For more information about synthetic modules, see <a href="https://msdn.microsoft.com/0cd99869-4014-4f9f-b5f1-d06c69fd134e">Synthetic Modules</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554536">RemoveSyntheticModule</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537943">AddSyntheticSymbol</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::AddSyntheticModule method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>