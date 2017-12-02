---
UID: NF.ntifs.RtlSelfRelativeToAbsoluteSD
title: RtlSelfRelativeToAbsoluteSD
author: windows-driver-content
description: The RtlSelfRelativeToAbsoluteSD routine creates a new security descriptor in absolute format by using a security descriptor in self-relative format as a template.
old-location: ifsk\rtlselfrelativetoabsolutesd.htm
old-project: ifsk
ms.assetid: 31565c5f-a1f2-4a81-bb91-e30e13f45050
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RtlSelfRelativeToAbsoluteSD
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
req.alt-api: RtlSelfRelativeToAbsoluteSD
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
req.iface: 
---

# RtlSelfRelativeToAbsoluteSD function



## -description
<p>The <b>RtlSelfRelativeToAbsoluteSD</b> routine creates a new security descriptor in absolute format by using a security descriptor in self-relative format as a template. </p>


## -syntax

````
NTSTATUS RtlSelfRelativeToAbsoluteSD(
  _In_    PSECURITY_DESCRIPTOR SelfRelativeSecurityDescriptor,
  _Out_   PSECURITY_DESCRIPTOR AbsoluteSecurityDescriptor,
  _Inout_ PULONG               AbsoluteSecurityDescriptorSize,
  _Out_   PACL                 Dacl,
  _Inout_ PULONG               DaclSize,
  _Out_   PACL                 Sacl,
  _Inout_ PULONG               SaclSize,
  _Out_   PSID                 Owner,
  _Inout_ PULONG               OwnerSize,
  _Out_   PSID                 PrimaryGroup,
  _Inout_ PULONG               PrimaryGroupSize
);
````


## -parameters
<dl>

### -param SelfRelativeSecurityDescriptor [in]

<dd>
<p>Pointer to a caller-allocated buffer that contains a SECURITY_DESCRIPTOR structure in self-relative format. <b>RtlSelfRelativeToAbsoluteSD</b> creates a version of this security descriptor in absolute format without modifying the original. </p>
</dd>

### -param AbsoluteSecurityDescriptor [out]

<dd>
<p>Pointer to a caller-allocated buffer that receives the main body of an absolute-format security descriptor. This information is formatted as a SECURITY_DESCRIPTOR structure. </p>
</dd>

### -param AbsoluteSecurityDescriptorSize [in, out]

<dd>
<p>Pointer to a caller-allocated variable that specifies the size, in bytes, of the buffer pointed to by the <i>AbsoluteSecurityDescriptor</i> parameter. If the buffer is not large enough to hold the security descriptor, <b>RtlSelfRelativeToAbsoluteSD</b> returns STATUS_BUFFER_TOO_SMALL and sets this variable to the minimum required size. </p>
</dd>

### -param Dacl [out]

<dd>
<p>Pointer to a caller-allocated buffer that receives the DACL of the absolute-format security descriptor. The main body of the absolute-format security descriptor references this pointer. </p>
</dd>

### -param DaclSize [in, out]

<dd>
<p>Pointer to a caller-allocated variable that specifies the size, in bytes, of the buffer pointed to by the <i>Dacl</i> parameter. If the buffer is not large enough to hold the DACL, <b>RtlSelfRelativeToAbsoluteSD</b> returns STATUS_BUFFER_TOO_SMALL and sets this variable to the minimum required size. </p>
</dd>

### -param Sacl [out]

<dd>
<p>Pointer to a caller-allocated buffer that receives the SACL of the absolute-format security descriptor. The main body of the absolute-format security descriptor references this pointer. </p>
</dd>

### -param SaclSize [in, out]

<dd>
<p>Pointer to a caller-allocated variable that specifies the size, in bytes, of the buffer pointed to by the <i>Sacl</i> parameter. If the buffer is not large enough to hold the SACL, <b>RtlSelfRelativeToAbsoluteSD</b> returns STATUS_BUFFER_TOO_SMALL and sets this variable to the minimum required size. </p>
</dd>

### -param Owner [out]

<dd>
<p>Pointer to a caller-allocated buffer that receives the SID of the owner of the absolute-format security descriptor. The main body of the absolute-format security descriptor references this pointer. </p>
</dd>

### -param OwnerSize [in, out]

<dd>
<p>Pointer to a caller-allocated variable that specifies the size, in bytes, of the buffer pointed to by the <i>Owner</i> parameter. If the buffer is not large enough to hold the SID, <b>RtlSelfRelativeToAbsoluteSD</b> returns STATUS_BUFFER_TOO_SMALL and sets this variable to the minimum required size. </p>
</dd>

### -param PrimaryGroup [out]

<dd>
<p>Pointer to a caller-allocated buffer that receives the SID of the primary group of the absolute-format security descriptor. The main body of the absolute-format security descriptor references this pointer. </p>
</dd>

### -param PrimaryGroupSize [in, out]

<dd>
<p>Pointer to a caller-allocated variable that specifies the size, in bytes, of the buffer pointed to by the <i>PrimaryGroup</i> parameter. If the buffer is not large enough to hold the SID, <b>RtlSelfRelativeToAbsoluteSD</b> returns STATUS_BUFFER_TOO_SMALL and sets this variable to the minimum required size. </p>
</dd>
</dl>

## -returns
<p><b>RtlSelfRelativeToAbsoluteSD</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:</p><dl>
<dt><b>STATUS_BAD_DESCRIPTOR_FORMAT</b></dt>
</dl><p>The buffer pointed to by the <i>AbsoluteSecurityDescriptor</i> parameter did not contain a SECURITY_DESCRIPTOR structure in absolute format. STATUS_BAD_DESCRIPTOR_FORMAT is an error code. </p><dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl><p>The buffer pointed to by the <i>AbsoluteSecurityDescriptor</i> , <i>Dacl</i>, <i>Sacl</i>, <i>Owner</i>, or <i>PrimaryGroup</i> parameter was too small. STATUS_BUFFER_TOO_SMALL is an error code. </p>

<p> </p>

## -remarks
<p>A security descriptor in absolute format contains pointers to the information, rather than containing the information itself. A security descriptor in self-relative format contains the information in a contiguous block of memory. In a self-relative security descriptor, a SECURITY_DESCRIPTOR structure always starts the information, but the security descriptor's other components can follow the SECURITY_DESCRIPTOR structure in any order. Instead of using memory addresses, the components of the security descriptor are identified by offsets from the beginning of the security descriptor. This format is useful when a security descriptor must be stored on a floppy disk or transmitted by means of a communications protocol. </p>

<p>Note that the <i>AbsoluteSecurityDescriptor</i> parameter receives only the main body of the absolute security descriptor. The entire absolute security descriptor consists of this main body, plus all of the security descriptor components returned in the <i>Dacl</i>, <i>Sacl</i>, <i>Owner</i>, and <i>PrimaryGroup</i> buffers. Thus, the caller cannot free these buffers after calling <b>RtlSelfRelativeToAbsoluteSD</b>, because doing so would invalidate the absolute security descriptor. </p>

<p>To create a new security descriptor in self-relative format by using a security descriptor in absolute format as a template, use <a href="..\ntifs\nf-ntifs-rtlabsolutetoselfrelativesd.md">RtlAbsoluteToSelfRelativeSD</a>. </p>

<p>For more information about security and access control, see the Microsoft Windows SDK documentation.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>This routine is available on Microsoft Windows Server 2003 SP1 and later. </p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntifs\ns-ntifs--acl.md">ACL</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlabsolutetoselfrelativesd.md">RtlAbsoluteToSelfRelativeSD</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlcreatesecuritydescriptor.md">RtlCreateSecurityDescriptor</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtllengthsecuritydescriptor.md">RtlLengthSecurityDescriptor</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlsetdaclsecuritydescriptor.md">RtlSetDaclSecurityDescriptor</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlsetownersecuritydescriptor.md">RtlSetOwnerSecurityDescriptor</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlvalidsecuritydescriptor.md">RtlValidSecurityDescriptor</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlSelfRelativeToAbsoluteSD routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
