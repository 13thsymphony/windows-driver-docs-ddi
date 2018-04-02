---
UID: NF:pep_x.PoFxRegisterPluginEx
title: PoFxRegisterPluginEx function
author: windows-driver-content
description: The PoFxRegisterPluginEx routine registers a platform extension plug-in (PEP) with the Windows power management framework (PoFx).
old-location: kernel\pofxregisterpluginex.htm
old-project: kernel
ms.assetid: 68753690-A6DC-46BE-9981-F395B98C3245
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: PoFxRegisterPluginEx, PoFxRegisterPluginEx routine [Kernel-Mode Driver Architecture], kernel.pofxregisterpluginex, pepfx/PoFxRegisterPluginEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
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
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ntoskrnl.lib
-	ntoskrnl.dll
api_name:
-	PoFxRegisterPluginEx
product:
- Windows
targetos: Windows
req.typenames: PEP_WORK_TYPE, *PPEP_WORK_TYPE, PEP_WORK_TYPE, *PPEP_WORK_TYPE
---


# PoFxRegisterPluginEx function
The <b>PoFxRegisterPluginEx</b> routine registers a platform extension plug-in (PEP) with the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).

## Syntax

```
NTKERNELAPI NTSTATUS PoFxRegisterPluginEx(
  PPEP_INFORMATION        PepInformation,
  ULONGLONG               Flags,
  PPEP_KERNEL_INFORMATION KernelInformation
);
```

## Parameters

`PepInformation`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186745">PEP_INFORMATION</a> structure that contains pointers to one or more callback routines that are implemented by the PEP. These routines handle notifications that are sent to the PEP by PoFx.

`Flags`

A set of flag bits for configuring the PEP interface. Set this member to zero or to the following value.

<table>
<tr>
<th>Flag bit</th>
<th>Description</th>
</tr>
<tr>
<td>PEP_FLAG_WORKER_CONCURRENCY</td>
<td></td>
</tr>
</table>

`KernelInformation`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt629114">PEP_KERNEL_INFORMATION</a> structure.


## Return Value

<b>PoFxRegisterPluginEx</b> returns STATUS_SUCCESS if the call successfully registers the PEP. Possible error return values include the following status codes.

<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>
</td>
<td width="60%">
The <b>Version</b> or <b>Size</b> member of the <b>PEP_KERNEL_INFORMATION</b> structure is set to an invalid value; or the <b>AcceptDeviceNotification</b> member of this structure is set to NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_INVALID_PEP_INFO_VERSION</dt>
</dl>
</td>
<td width="60%">
The <b>Version</b> member of the <b>PEP_INFORMATION</b> structure is set to an invalid value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_INSUFFICIENT_RESOURCES</dt>
</dl>
</td>
<td width="60%">
Unable to allocate the resources required to complete the requested registration.

</td>
</tr>
</table>

## Remarks

A PEP calls this routine to register itself with PoFx.

A PEP cannot unregister, and cannot register twice. If the PEP must be serviced, the operating system must restart.

The <a href="https://msdn.microsoft.com/library/windows/hardware/mt186873">PoFxRegisterPlugin</a> routine is similar to <b>PoFxRegisterPluginEx</b>, except that it does not take a <i>Flags</i> parameter.

The PEP must call <b>PoFxRegisterPluginEx</b> at IRQL = PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 10.  |
| **Target Platform** | Windows |
| **Header** | pep_x.h (include Pep_x.h) |
| **Library** | Ntoskrnl.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt186745">PEP_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt629114">PEP_KERNEL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186873">PoFxRegisterPlugin</a>