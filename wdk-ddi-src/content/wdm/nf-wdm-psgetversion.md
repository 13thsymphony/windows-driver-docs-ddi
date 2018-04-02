---
UID: NF:wdm.PsGetVersion
title: PsGetVersion function
author: windows-driver-content
description: This function is obsolete in Windows XP and later versions of the Windows operating system. Use RtlGetVersion instead.PsGetVersion returns caller-selected information about the current version of the NT-based operating system.
old-location: kernel\psgetversion.htm
old-project: kernel
ms.assetid: db3d2e34-3d83-423d-b446-2800d53a8220
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: PsGetVersion, PsGetVersion function [Kernel-Mode Driver Architecture], k108_3c73c1e7-3f02-4598-adae-43c378dcfb08.xml, kernel.psgetversion, wdm/PsGetVersion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlPsPassive, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsGetVersion
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# PsGetVersion function
This function is <u>obsolete</u> in Windows XP and later versions of the Windows operating system. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff561910">RtlGetVersion</a> instead.

<b>PsGetVersion</b> returns caller-selected information about the current version of the NT-based operating system.

## Syntax

```
NTKERNELAPI BOOLEAN PsGetVersion(
  PULONG          MajorVersion,
  PULONG          MinorVersion,
  PULONG          BuildNumber,
  PUNICODE_STRING CSDVersion
);
```

## Parameters

`MajorVersion`

Points to a caller-supplied variable that this routine sets to the major version of the operating system. This optional parameter can be <b>NULL</b>.

`MinorVersion`

Points to a caller-supplied variable that this routine sets to the minor version of the operating system. This optional parameter can be <b>NULL</b>.

`BuildNumber`

Points to a caller-supplied variable that this routine sets to the current build number of the operating system. This optional parameter can be <b>NULL</b>.

`CSDVersion`

Points to a caller-allocated buffer in which this routine returns the current service-pack version as a Unicode string only during system driver initialization. This optional parameter can be <b>NULL</b>.


## Return Value

<b>PsGetVersion</b> returns whether the system is a checked or free build, as follows:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>TRUE</b> (1)</b></dt>
</dl>
</td>
<td width="60%">
Checked build of the operating system.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>FALSE</b> (0)</b></dt>
</dl>
</td>
<td width="60%">
Free build of the operating system. 

</td>
</tr>
</table>

## Remarks

<b>PsGetVersion</b> returns the requested information, depending on which optional parameter(s) the caller supplies.

To retrieve the current service-pack number, it is easier and more efficient to make an application-level call within the Win32 environment than to call <b>PsGetVersion</b> during system driver initialization, which then must parse the string it returns at <i>CSDVersion</i>. When the registry is initialized, a driver cannot obtain this string from <b>PsGetVersion</b>, but must read the <b>CmCSDVersionString</b> value from the registry.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | IrqlPsPassive, PowerIrpDDis, HwStorPortProhibitedDDIs |