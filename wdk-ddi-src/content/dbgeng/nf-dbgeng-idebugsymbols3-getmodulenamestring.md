---
UID: NF:dbgeng.IDebugSymbols3.GetModuleNameString
title: IDebugSymbols3::GetModuleNameString method
author: windows-driver-content
description: The GetModuleNameString method returns the name of the specified module.
old-location: debugger\getmodulenamestring.htm
old-project: debugger
ms.assetid: 4264f5e1-08f5-4878-9e10-b98859043515
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetModuleNameString method [Windows Debugging], dbgeng/IDebugSymbols2::GetModuleNameString, IDebugSymbols2::GetModuleNameString, IDebugSymbols2 interface [Windows Debugging], GetModuleNameString method, GetModuleNameString, debugger.getmodulenamestring, GetModuleNameString method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols3::GetModuleNameString, GetModuleNameString method [Windows Debugging], IDebugSymbols2 interface, IDebugSymbols2, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetModuleNameString method, IDebugSymbols_e00a93fb-08c4-4f37-9915-577a22d9c889.xml, dbgeng/IDebugSymbols3::GetModuleNameString
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugSymbols2.GetModuleNameString
-	IDebugSymbols3.GetModuleNameString
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetModuleNameString method
The <b>GetModuleNameString</b>  method returns the name of the specified module.

## Syntax

````
HRESULT GetModuleNameString(
  [in]            ULONG   Which,
  [in]            ULONG   Index,
  [in]            ULONG64 Base,
  [out, optional] PSTR    Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  NameSize
);
````

## Parameters

`Which`

Specifies which of the module's names to return, possible values are:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_MODNAME_IMAGE

</td>
<td>
The image name.  This is the name of the executable file, including the extension. Typically, the full path is included in user mode but not in kernel mode.

</td>
</tr>
<tr>
<td>
DEBUG_MODNAME_MODULE

</td>
<td>
The module name. This is usually just the file name without the extension. In a few cases, the module name differs significantly from the file name.

</td>
</tr>
<tr>
<td>
DEBUG_MODNAME_LOADED_IMAGE

</td>
<td>
The loaded image name.  Unless Microsoft CodeView symbols are present, this is the same as the image name.

</td>
</tr>
<tr>
<td>
DEBUG_MODNAME_SYMBOL_FILE

</td>
<td>
The symbol file name.  The path and name of the symbol file. If no symbols have been loaded, this is the name of the executable file instead.

</td>
</tr>
<tr>
<td>
DEBUG_MODNAME_MAPPED_IMAGE

</td>
<td>
The mapped image name.  In most cases, this is <b>NULL</b>. If the debugger is mapping an image file (for example, during minidump debugging), this is the name of the mapped image.

</td>
</tr>
</table>

`Index`

Specifies the index of the module.  If it is set to DEBUG_ANY_ID, the <i>Base</i> parameter is used to specify the location of the module instead.

`Base`

If <i>Index</i> is DEBUG_ANY_ID, specifies the location in the target's memory address space of the base of the module.  Otherwise it is ignored.

`Buffer`

Receives the name of the module.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.

`BufferSize`

Specifies the size in characters of the buffer <i>Buffer</i>.

`NameSize`

Receives the size in characters of the module's name.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


## Return Value

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful. However, the size of the buffer was smaller than the size of the module's name so it was truncated to fit in the buffer.

</td>
</tr>
</table>

## Remarks

For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547146">GetModuleNames</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols2::GetModuleNameString method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>