---
UID: NF:dbgeng.IDebugSymbols3.AddSyntheticSymbol
title: IDebugSymbols3::AddSyntheticSymbol method
author: windows-driver-content
description: The AddSyntheticSymbol method adds a synthetic symbol to a module in the current process.
old-location: debugger\addsyntheticsymbol.htm
old-project: debugger
ms.assetid: 17fe1fbc-ca55-4d4d-af79-73baad410bfb
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: AddSyntheticSymbol method [Windows Debugging], AddSyntheticSymbol method [Windows Debugging], IDebugSymbols3 interface, AddSyntheticSymbol,IDebugSymbols3.AddSyntheticSymbol, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], AddSyntheticSymbol method, IDebugSymbols3::AddSyntheticSymbol, IDebugSymbols_8dcf97a7-eb9c-44aa-a2a7-1ad74cb396c1.xml, dbgeng/IDebugSymbols3::AddSyntheticSymbol, debugger.addsyntheticsymbol
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
req.lib: 
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
-	IDebugSymbols3.AddSyntheticSymbol
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# AddSyntheticSymbol method
The <b>AddSyntheticSymbol</b>  method adds a synthetic symbol to a module in the <a href="https://msdn.microsoft.com/295b05a3-e27f-4761-a562-7e87e25bfd3b">current process</a>.

## Syntax

````
HRESULT AddSyntheticSymbol(
  [in]            ULONG64              Offset,
  [in]            ULONG                Size,
  [in]            PCSTR                Name,
  [in]            ULONG                Flags,
  [out, optional] PDEBUG_MODULE_AND_ID Id
);
````

## Parameters

`Offset`

Specifies the location in the process's virtual address space of the synthetic symbol.

`Size`

Specifies the size in bytes of the synthetic symbol.

`Name`

Specifies the name of the synthetic symbol.

`Flags`

Set to DEBUG_ADDSYNTHSYM_DEFAULT.

`Id`

Receives the <a href="..\dbgeng\ns-dbgeng-_debug_module_and_id.md">DEBUG_MODULE_AND_ID</a> structure that identifies the synthetic symbol.  If <i>Id</i> is <b>NULL</b>, this information is not returned.


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

The location of the synthetic symbol must not be the same as the location of another symbol.

If the module containing a synthetic symbol is reloaded - for example, by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554379">Reload</a> with the <i>Module</i> parameter set to the name of the module - the synthetic symbol will be discarded.

For more information about synthetic symbols, see <a href="https://msdn.microsoft.com/1de1441f-b4d7-49e9-87ad-392a75b3d4be">Synthetic Symbols</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554542">RemoveSyntheticSymbol</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537937">AddSyntheticModule</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::AddSyntheticSymbol method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>