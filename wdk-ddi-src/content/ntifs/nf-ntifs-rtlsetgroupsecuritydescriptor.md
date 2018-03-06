---
UID: NF:ntifs.RtlSetGroupSecurityDescriptor
title: RtlSetGroupSecurityDescriptor function
author: windows-driver-content
description: The RtlSetGroupSecurityDescriptor routine sets the primary group information of an absolute-format security descriptor. It replaces any primary group information that is already present in the security descriptor.
old-location: ifsk\rtlsetgroupsecuritydescriptor.htm
old-project: ifsk
ms.assetid: f0473975-7ab6-46ba-bdb7-eb227e6bc258
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlSetGroupSecurityDescriptor, RtlSetGroupSecurityDescriptor routine [Installable File System Drivers], ifsk.rtlsetgroupsecuritydescriptor, ntifs/RtlSetGroupSecurityDescriptor, rtlref_113e5ca7-5db3-4c93-a26f-c568e2164de9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows Server 2003 SP1 and later.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlSetGroupSecurityDescriptor
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlSetGroupSecurityDescriptor function
The <b>RtlSetGroupSecurityDescriptor</b> routine sets the primary group information of an absolute-format security descriptor. It replaces any primary group information that is already present in the security descriptor.

## Syntax

````
NTSTATUS RtlSetGroupSecurityDescriptor(
  _Inout_  PSECURITY_DESCRIPTOR SecurityDescriptor,
  _In_opt_ PSID                 Group,
  _In_opt_ BOOLEAN              GroupDefaulted
);
````

## Parameters

`SecurityDescriptor`

Pointer to the <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> structure whose primary group is to be set. <b>RtlSetGroupSecurityDescriptor</b> replaces any existing primary group with the new primary group.

`Group`

Pointer to a security identifier (<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>) structure for the security descriptor's new primary owner. This pointer, not the SID structure itself, is copied into the security descriptor. If <i>Group</i> is <b>NULL</b>, <b>RtlSetGroupSecurityDescriptor</b> clears the security descriptor's primary group information. This marks the security descriptor as having no primary group.

`GroupDefaulted`

Set this Boolean variable to <b>TRUE</b> if the primary group information is derived from a default mechanism. If this parameter is <b>TRUE</b>, <b>RtlSetGroupSecurityDescriptor</b> sets the SE_GROUP_DEFAULTED flag in the security descriptor's SECURITY_DESCRIPTOR_CONTROL field. If this parameter is <b>FALSE</b>, <b>RtlSetGroupSecurityDescriptor</b> clears the SE_GROUP_DEFAULTED flag.


## Return Value

<b>RtlSetGroupSecurityDescriptor</b> returns STATUS_SUCCESS if the primary group was successfully set or reset. Otherwise, it returns an appropriate NTSTATUS value such as one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_SECURITY_DESCR</b></dt>
</dl>
</td>
<td width="60%">
The given security descriptor is not a valid absolute security descriptor. STATUS_INVALID_SECURITY_DESCR is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNKNOWN_REVISION</b></dt>
</dl>
</td>
<td width="60%">
The given security descriptor's revision is not recognized by this routine. STATUS_UNKNOWN_REVISION is an error code. 

</td>
</tr>
</table>

## Remarks

To retrieve the primary group information for a security descriptor, use <a href="..\ntifs\nf-ntifs-rtlgetgroupsecuritydescriptor.md">RtlGetGroupSecurityDescriptor</a>. 

To set the owner information for a security descriptor, use <a href="..\ntifs\nf-ntifs-rtlsetownersecuritydescriptor.md">RtlSetOwnerSecurityDescriptor</a>. 

For more information about security and access control, see the Microsoft Windows SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This routine is available on Microsoft Windows Server 2003 SP1 and later.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe (kernel mode); Ntdll.dll (user mode) |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-rtlsetownersecuritydescriptor.md">RtlSetOwnerSecurityDescriptor</a>



<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="..\ntifs\nf-ntifs-rtlgetgroupsecuritydescriptor.md">RtlGetGroupSecurityDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556619">SECURITY_DESCRIPTOR_CONTROL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlSetGroupSecurityDescriptor routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>