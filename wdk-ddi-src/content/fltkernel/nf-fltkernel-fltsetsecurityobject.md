---
UID: NF.fltkernel.FltSetSecurityObject
title: FltSetSecurityObject function
author: windows-driver-content
description: FltSetSecurityObject sets an object's security state.
old-location: ifsk\fltsetsecurityobject.htm
old-project: ifsk
ms.assetid: 3276dff3-d12a-4a30-bbdc-a582a2228df3
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltSetSecurityObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltSetSecurityObject
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL
---

# FltSetSecurityObject function



## -description
<b>FltSetSecurityObject</b> sets an object's security state. 


## -syntax

````
NTSTATUS FltSetSecurityObject(
  _In_ PFLT_INSTANCE        Instance,
  _In_ PFILE_OBJECT         FileObject,
  _In_ SECURITY_INFORMATION SecurityInformation,
  _In_ PSECURITY_DESCRIPTOR SecurityDescriptor
);
````


## -parameters

### -param Instance [in]

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 

### -param FileObject [in]

File object pointer for the object whose security state is to be set. The caller must have the access specified in the Meaning column of the table shown in the description of the <i>SecurityInformation</i> parameter. This parameter is required and cannot be <b>NULL</b>. 

### -param SecurityInformation [in]

Pointer to a <a href="ifsk.security_information">SECURITY_INFORMATION</a> value specifying the information to be set as a combination of one or more of the following. This parameter is required and cannot be <b>NULL</b>. 
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DACL_SECURITY_INFORMATION
</td>
<td>
Indicates the discretionary access control list (DACL) of the object is to be set. Requires WRITE_DAC access. 
</td>
</tr>
<tr>
<td>
GROUP_SECURITY_INFORMATION
</td>
<td>
Indicates the primary group identifier of the object is to be set. Requires WRITE_OWNER access. 
</td>
</tr>
<tr>
<td>
OWNER_SECURITY_INFORMATION
</td>
<td>
Indicates the owner identifier of the object is to be set. Requires WRITE_OWNER access. 
</td>
</tr>
<tr>
<td>
SACL_SECURITY_INFORMATION
</td>
<td>
Indicates the system ACL (SACL) of the object is to be set. Requires ACCESS_SYSTEM_SECURITY access. 
</td>
</tr>
</table>
 

### -param SecurityDescriptor [in]

Pointer to the security descriptor to be set for the object. 

## -returns
<b>FltSetSecurityObject</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The caller did not have the required access. This is an error code. 
<dl>
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
</dl><i>SecurityDescriptor</i> was a <b>NULL</b> pointer. This is an error code. 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The object's security descriptor could not be captured. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_ACL</b></dt>
</dl>The object's security descriptor contained an invalid ACL. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_SECURITY_DESCR</b></dt>
</dl><i>SecurityDescriptor</i> did not point to a valid security descriptor. This is an error code. 
<dl>
<dt><b>STATUS_INVALID_SID</b></dt>
</dl>The object's security descriptor contained an invalid SID. This is an error code. 
<dl>
<dt><b>STATUS_UNKNOWN_REVISION</b></dt>
</dl>The revision level of the object's security descriptor was unknown or not supported. This is an error code. 
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>The <b>FltSetSecurityObject</b> routine is present but not supported in the operating system environment in which it was called.

 

## -remarks
The <b>FltSetSecurityObject</b> routine is present and supported starting with Windows Vista.  In Windows 2000, Windows XP, and Server 2003 SP1, the routine is present but not supported, and will return STATUS_NOT_IMPLEMENTED if called in any of these environments.

A security descriptor can be in absolute or self-relative form. In self-relative form, all members of the structure are located contiguously in memory. In absolute form, the structure only contains pointers to the members. For more information, see "Absolute and Self-Relative Security Descriptors" in the Security section of the Microsoft Windows SDK documentation. 

For more information about security and access control, see the documentation on these topics in the Windows SDK. 

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
Header
</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>Fltmgr.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fltquerysecurityobject">FltQuerySecurityObject</a>
</dt>
<dt>
<a href="ifsk.security_descriptor">SECURITY_DESCRIPTOR</a>
</dt>
<dt>
<a href="ifsk.security_information">SECURITY_INFORMATION</a>
</dt>
<dt>
<a href="kernel.zwquerysecurityobject">ZwQuerySecurityObject</a>
</dt>
<dt>
<a href="kernel.zwsetsecurityobject">ZwSetSecurityObject</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltSetSecurityObject function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
