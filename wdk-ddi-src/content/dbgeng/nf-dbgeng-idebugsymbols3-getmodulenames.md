---
UID : NF:dbgeng.IDebugSymbols3.GetModuleNames
title : IDebugSymbols3::GetModuleNames method
author : windows-driver-content
description : The GetModuleNames method returns the names of the specified module.
old-location : debugger\getmodulenames.htm
old-project : debugger
ms.assetid : dd33f88a-91f6-4ea4-bb6b-6fb505676684
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugSymbols3, IDebugSymbols3::GetModuleNames, GetModuleNames
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
req.alt-api : IDebugSymbols.GetModuleNames,IDebugSymbols2.GetModuleNames,IDebugSymbols3.GetModuleNames
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


# GetModuleNames method
The <b>GetModuleNames</b> method returns the names of the specified module.

## Syntax

````
HRESULT GetModuleNames(
  [in]            ULONG   Index,
  [in]            ULONG64 Base,
  [out, optional] PSTR    ImageNameBuffer,
  [in]            ULONG   ImageNameBufferSize,
  [out, optional] PULONG  ImageNameSize,
  [out, optional] PSTR    ModuleNameBuffer,
  [in]            ULONG   ModuleNameBufferSize,
  [out, optional] PULONG  ModuleNameSize,
  [out, optional] PSTR    LoadedImageNameBuffer,
  [in]            ULONG   LoadedImageNameBufferSize,
  [out, optional] PULONG  LoadedImageNameSize
);
````

## Parameters

`Index`

Specifies the index of the module whose names are requested.  If it is set to DEBUG_ANY_ID, the module is specified by <i>Base</i>.

`Base`

Specifies the base address of the module whose names are requested.  This parameter is only used if <i>Index</i> is set to DEBUG_ANY_ID.

`ImageNameBuffer`

Receives the image name of the module.  If <i>ImageNameBuffer</i> is <b>NULL</b>, this information is not returned.

`ImageNameBufferSize`

Specifies the size in characters of the buffer <i>ImageNameBuffer</i> in characters.

`ImageNameSize`

Receives the size in characters of the image name.  If <i>ImageNameSize</i> is <b>NULL</b>, this information is not returned.

`ModuleNameBuffer`

Receives the module name of the module.  If <i>ModuleNameBuffer</i> is <b>NULL</b>, this information is not returned.

`ModuleNameBufferSize`

Specifies the size in characters of the buffer <i>ModuleNameBuffer</i>.

`ModuleNameSize`

Receives the size in characters of the module name.  If <i>ModuleNameSize</i> is <b>NULL</b>, this information is not returned.

`LoadedImageNameBuffer`

Receives the loaded image name of the module.  If <i>LoadedImageNameBuffer</i> is <b>NULL</b>, this information is not returned.

`LoadedImageNameBufferSize`

Specifies the size in characters of the buffer <i>LoadedImageNameBuffer</i>.

`LoadedImageNameSize`

Receives the size in characters of the loaded image name.  If <i>LoadedImageNameSize</i> is <b>NULL</b>, this information is not returned.


## Return Value

This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The method was successful. However, at least one of <i>ImageNameBuffer</i>, <i>ModuleNameBuffer</i>, or <i>LoadedImageNameBuffer</i> was too small for the corresponding name, so it was truncated.
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>The specified module was not found.

## Remarks

For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.

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
<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547149">GetModuleNameString</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::GetModuleNames method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>