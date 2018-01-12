---
UID: NF:dbgeng.IDebugRegisters2.GetPseudoIndexByName
title: IDebugRegisters2::GetPseudoIndexByName method
author: windows-driver-content
description: The GetPseudoIndexByName method returns the index of a pseudo-register.
old-location: debugger\getpseudoindexbyname.htm
old-project: debugger
ms.assetid: 0973d8d8-53df-47aa-be65-71045c2e6006
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugRegisters2, IDebugRegisters2::GetPseudoIndexByName, GetPseudoIndexByName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugRegisters2.GetPseudoIndexByName
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

# IDebugRegisters2::GetPseudoIndexByName method



## -description
The <b>GetPseudoIndexByName</b>  method returns the index of a pseudo-register.



## -syntax

````
HRESULT GetPseudoIndexByName(
  [in]  PCSTR  Name,
  [out] PULONG Index
);
````


## -parameters

### -param Name [in]

Specifies the name of the pseudo-register whose index is requested.  The name includes the leading dollar sign ( <b>$</b> ), for example, "$frame".


### -param Index [out]

Receives the index of the pseudo-register.


## -returns
This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 


## -remarks
For the names of all the pseudo-registers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553485">Pseudo-Register Syntax</a>.

For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.


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
<dt>Dbgeng.h (include DbgEng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugregisters2.md">IDebugRegisters2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548189">GetPseudoDescription</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugRegisters2::GetPseudoIndexByName method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

