---
UID: NF:wdm.RtlSetDaclSecurityDescriptor
title: RtlSetDaclSecurityDescriptor function
author: windows-driver-content
description: The RtlSetDaclSecurityDescriptor routine sets the DACL information of an absolute-format security descriptor, or if there is already a DACL present in the security descriptor, it is superseded.
old-location: kernel\rtlsetdaclsecuritydescriptor.htm
old-project: kernel
ms.assetid: d22f4a14-2293-4210-bead-5814484a1471
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlSetDaclSecurityDescriptor, RtlSetDaclSecurityDescriptor routine [Kernel-Mode Driver Architecture], k109_b2723172-ac75-4ada-b421-ae144d10d560.xml, kernel.rtlsetdaclsecuritydescriptor, wdm/RtlSetDaclSecurityDescriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlSetDaclSecurityDescriptor
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlSetDaclSecurityDescriptor function
The <b>RtlSetDaclSecurityDescriptor</b> routine sets the DACL information of an absolute-format security descriptor, or if there is already a DACL present in the security descriptor, it is superseded.

## Syntax

```
NTSYSAPI NTSTATUS RtlSetDaclSecurityDescriptor(
  PSECURITY_DESCRIPTOR SecurityDescriptor,
  BOOLEAN              DaclPresent,
  PACL                 Dacl,
  BOOLEAN              DaclDefaulted
);
```

## Parameters

`SecurityDescriptor`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a> structure. This structure is the security descriptor to which the DACL is to be applied.

`DaclPresent`

Whether to indicate that a DACL is present in the security descriptor. If this parameter is <b>FALSE</b>, <b>RtlSetDaclSecurityDescriptor</b> sets the SE_DACL_PRESENT control flag in the security descriptor to <b>FALSE</b>. In this case, the remaining optional parameters (<i>Dacl</i> and <i>DaclDefaulted</i>) are ignored. If <i>DaclPresent</i> is <b>TRUE</b>, the SE_DACL_PRESENT flag in the security descriptor is set to <b>TRUE</b> and the remaining optional parameters are <u>not</u> ignored. For more information about the SE_DACL_PRESENT flag, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556619">SECURITY_DESCRIPTOR_CONTROL</a>.

`Dacl`

A pointer to the DACL for the security descriptor. If this parameter is <b>NULL</b>, the DACL pointer in the security descriptor is set to <b>NULL</b>. A <b>NULL</b> DACL pointer unconditionally grants all access to an object and is not the same as an empty DACL. An empty DACL denies all access to an object. If <i>Dacl</i> is non-<b>NULL</b>, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a> structure supplied by the caller is referenced by, but not copied into, the security descriptor. The caller can allocate the <b>ACL</b> structure from paged system memory, and can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552151">RtlCreateAcl</a> routine to initialize the structure.

`DaclDefaulted`

Whether the DACL was supplied by some default mechanism, or was explicitly specified by the caller. If this parameter is <b>TRUE</b>, the DACL was supplied by a default mechanism. If <i>DaclDefaulted</i> is <b>FALSE</b>, the caller explicitly specified the DACL. <b>RtlSetDaclSecurityDescriptor</b> copies the value specified for this parameter to the SE_DACL_DEFAULTED control flag in the security descriptor. For more information about the SE_DACL_DEFAULTED flag, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556619">SECURITY_DESCRIPTOR_CONTROL</a>.


## Return Value

<b>RtlSetDaclSecurityDescriptor</b> can return one of the following status values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The call completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNKNOWN_REVISION</b></dt>
</dl>
</td>
<td width="60%">
The revision of the security descriptor is unknown.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_SECURITY_DESCR</b></dt>
</dl>
</td>
<td width="60%">
The security descriptor is not an absolute format security descriptor.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe (kernel mode); Ntdll.dll (user mode) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff538866">ACL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552151">RtlCreateAcl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561827">RtlCreateSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562025">RtlLengthSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563024">RtlValidSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556619">SECURITY_DESCRIPTOR_CONTROL</a>