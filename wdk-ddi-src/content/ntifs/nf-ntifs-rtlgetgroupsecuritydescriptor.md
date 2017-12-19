---
UID: NF.ntifs.RtlGetGroupSecurityDescriptor
title: RtlGetGroupSecurityDescriptor function
author: windows-driver-content
description: The RtlGetGroupSecurityDescriptor routine returns the primary group information for a given security descriptor.
old-location: ifsk\rtlgetgroupsecuritydescriptor.htm
old-project: ifsk
ms.assetid: a2fbb125-42cf-4c33-83bb-3fc875712be3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RtlGetGroupSecurityDescriptor
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
req.alt-api: RtlGetGroupSecurityDescriptor
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
---

# RtlGetGroupSecurityDescriptor function



## -description
The <b>RtlGetGroupSecurityDescriptor</b> routine returns the primary group information for a given security descriptor.



## -syntax

````
NTSTATUS RtlGetGroupSecurityDescriptor(
  _In_  PSECURITY_DESCRIPTOR SecurityDescriptor,
  _Out_ PSID                 *Group,
  _Out_ PBOOLEAN             GroupDefaulted
);
````


## -parameters

### -param SecurityDescriptor [in]

Pointer to the security descriptor whose primary group information is to be returned.


### -param Group [out]

Pointer to a variable that receives a pointer to the security identifier (<a href="ifsk.sid">SID</a>) for the primary group. If the security descriptor does not contain a primary group, <i>*Group</i> receives <b>NULL</b>.


### -param GroupDefaulted [out]

Pointer to a Boolean variable that receives the value of the SE_GROUP_DEFAULTED flag in the security descriptor's SECURITY_DESCRIPTOR_CONTROL structure. This value is valid only if <i>*Group</i> receives a non-<b>NULL</b> value.


## -returns
<b>RtlGetGroupSecurityDescriptor</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following:
<dl>
<dt><b>STATUS_UNKNOWN_REVISION</b></dt>
</dl>The security descriptor's revision level is not known or is not supported. This is an error code. 

 


## -remarks
If the security descriptor pointed to by <i>SecurityDescriptor</i> contains a primary group, <b>RtlGetGroupSecurityDescriptor</b> sets the pointer pointed to by <i>Group</i> to the address of the security descriptor's group SID and sets the variable pointed to by <i>GroupDefaulted</i> to a valid value. 

If the security descriptor pointed to by <i>SecurityDescriptor</i> does not contain a primary group, <b>RtlGetGroupSecurityDescriptor</b> sets the pointer pointed to by <i>Group</i> to <b>NULL</b> and ignores the remaining output parameter, <i>GroupDefaulted</i>. 

To set the primary group information for a security descriptor, use <a href="ifsk.rtlsetgroupsecuritydescriptor">RtlSetGroupSecurityDescriptor</a>. 

To retrieve the owner information for a security descriptor, use <a href="ifsk.rtlgetownersecuritydescriptor">RtlGetOwnerSecurityDescriptor</a>. 

For more information about security and access control, see the Microsoft Windows SDK documentation.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
This routine is available on Microsoft Windows Server 2003 SP1 and later. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.rtlgetownersecuritydescriptor">RtlGetOwnerSecurityDescriptor</a>
</dt>
<dt>
<a href="ifsk.rtlsetgroupsecuritydescriptor">RtlSetGroupSecurityDescriptor</a>
</dt>
<dt>
<a href="ifsk.security_descriptor">SECURITY_DESCRIPTOR</a>
</dt>
<dt>
<a href="ifsk.sid">SID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlGetGroupSecurityDescriptor routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

