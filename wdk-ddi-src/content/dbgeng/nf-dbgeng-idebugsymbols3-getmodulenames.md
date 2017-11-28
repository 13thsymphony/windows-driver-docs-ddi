---
UID: NF.dbgeng.IDebugSymbols3.GetModuleNames
title: IDebugSymbols3::GetModuleNames
author: windows-driver-content
description: The GetModuleNames method returns the names of the specified module.
old-location: debugger\getmodulenames.htm
old-project: debugger
ms.assetid: dd33f88a-91f6-4ea4-bb6b-6fb505676684
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: IDebugSymbols3, GetModuleNames, IDebugSymbols3::GetModuleNames
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugSymbols.GetModuleNames,IDebugSymbols2.GetModuleNames,IDebugSymbols3.GetModuleNames
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
req.iface: IDebugSymbols3
---

# IDebugSymbols3::GetModuleNames method



## -description
<p>The <b>GetModuleNames</b> method returns the names of the specified module.</p>


## -syntax

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


## -parameters
<dl>

### -param <i>Index</i> [in]

<dd>
<p>Specifies the index of the module whose names are requested.  If it is set to DEBUG_ANY_ID, the module is specified by <i>Base</i>.</p>
</dd>

### -param <i>Base</i> [in]

<dd>
<p>Specifies the base address of the module whose names are requested.  This parameter is only used if <i>Index</i> is set to DEBUG_ANY_ID.</p>
</dd>

### -param <i>ImageNameBuffer</i> [out, optional]

<dd>
<p>Receives the image name of the module.  If <i>ImageNameBuffer</i> is <b>NULL</b>, this information is not returned.</p>
</dd>

### -param <i>ImageNameBufferSize</i> [in]

<dd>
<p>Specifies the size in characters of the buffer <i>ImageNameBuffer</i> in characters.</p>
</dd>

### -param <i>ImageNameSize</i> [out, optional]

<dd>
<p>Receives the size in characters of the image name.  If <i>ImageNameSize</i> is <b>NULL</b>, this information is not returned.</p>
</dd>

### -param <i>ModuleNameBuffer</i> [out, optional]

<dd>
<p>Receives the module name of the module.  If <i>ModuleNameBuffer</i> is <b>NULL</b>, this information is not returned.</p>
</dd>

### -param <i>ModuleNameBufferSize</i> [in]

<dd>
<p>Specifies the size in characters of the buffer <i>ModuleNameBuffer</i>.</p>
</dd>

### -param <i>ModuleNameSize</i> [out, optional]

<dd>
<p>Receives the size in characters of the module name.  If <i>ModuleNameSize</i> is <b>NULL</b>, this information is not returned.</p>
</dd>

### -param <i>LoadedImageNameBuffer</i> [out, optional]

<dd>
<p>Receives the loaded image name of the module.  If <i>LoadedImageNameBuffer</i> is <b>NULL</b>, this information is not returned.</p>
</dd>

### -param <i>LoadedImageNameBufferSize</i> [in]

<dd>
<p>Specifies the size in characters of the buffer <i>LoadedImageNameBuffer</i>.</p>
</dd>

### -param <i>LoadedImageNameSize</i> [out, optional]

<dd>
<p>Receives the size in characters of the loaded image name.  If <i>LoadedImageNameSize</i> is <b>NULL</b>, this information is not returned.</p>
</dd>
</dl>

## -returns
<p>This method may also return other error values.  See <a href="debugger.hresult_values">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p><dl>
<dt><b>S_FALSE</b></dt>
</dl><p>The method was successful. However, at least one of <i>ImageNameBuffer</i>, <i>ModuleNameBuffer</i>, or <i>LoadedImageNameBuffer</i> was too small for the corresponding name, so it was truncated.</p><dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl><p>The specified module was not found.</p>

<p> </p>

## -remarks
<p>For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.</p>

<p>For more information about modules, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547149">GetModuleNameString</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::GetModuleNames method%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
