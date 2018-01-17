---
UID: NF:fltkernel.FltBuildDefaultSecurityDescriptor
title: FltBuildDefaultSecurityDescriptor function
author: windows-driver-content
description: FltBuildDefaultSecurityDescriptor builds a default security descriptor for use with FltCreateCommunicationPort.
old-location: ifsk\fltbuilddefaultsecuritydescriptor.htm
old-project: ifsk
ms.assetid: 0e886c08-38dd-4960-9b79-4c6e68ac488d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltBuildDefaultSecurityDescriptor
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
req.alt-api: FltBuildDefaultSecurityDescriptor
req.alt-loc: FltMgr.lib,FltMgr.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: 
req.irql: <= APC_LEVEL
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# FltBuildDefaultSecurityDescriptor function



## -description
<b>FltBuildDefaultSecurityDescriptor</b> builds a default security descriptor for use with <a href="..\fltkernel\nf-fltkernel-fltcreatecommunicationport.md">FltCreateCommunicationPort</a>. 



## -syntax

````
NTSTATUS FltBuildDefaultSecurityDescriptor(
  _Out_ PSECURITY_DESCRIPTOR *SecurityDescriptor,
  _In_  ACCESS_MASK          DesiredAccess
);
````


## -parameters

### -param SecurityDescriptor [out]

Pointer to a caller-allocated variable that receives an opaque pointer to the newly created <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>. 


### -param DesiredAccess [in]

Bitmask of flags that specify the type of access that the caller requires to the port object. The set of system-defined <i>DesiredAccess</i> flags determines the following specific access rights for minifilter driver communication port objects. 

<table>
<tr>
<th>DesiredAccess Flags</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLT_PORT_CONNECT

</td>
<td>
The caller can connect to the port. 

</td>
</tr>
<tr>
<td>
FLT_PORT_ALL_ACCESS

</td>
<td>
FLT_PORT_CONNECT | STANDARD_RIGHTS_ALL

</td>
</tr>
</table>
 


## -returns
<b>FltBuildDefaultSecurityDescriptor</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><b>FltBuildDefaultSecurityDescriptor</b> encountered a pool allocation failure. This is an error code. 

 


## -remarks
When creating a minifilter driver communication port, a minifilter driver can call <b>FltBuildDefaultSecurityDescriptor</b> to create a default security descriptor for the port. The minifilter driver then creates the port by calling <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> and <a href="..\fltkernel\nf-fltkernel-fltcreatecommunicationport.md">FltCreateCommunicationPort</a>. The security descriptor is passed as a parameter to <b>InitializeObjectAttributes</b>. 

<b>FltBuildDefaultSecurityDescriptor</b> causes the system to allocate a default security descriptor from paged pool. When this security descriptor is applied to an object, only users with system or administrator privileges have access to the object. 

Minifilter drivers usually call <b>FltBuildDefaultSecurityDescriptor</b> immediately before calling <a href="..\fltkernel\nf-fltkernel-fltcreatecommunicationport.md">FltCreateCommunicationPort</a> and <a href="..\fltkernel\nf-fltkernel-fltfreesecuritydescriptor.md">FltFreeSecurityDescriptor</a> immediately after calling <b>FltCreateCommunicationPort</b>. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcreatecommunicationport.md">FltCreateCommunicationPort</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltfreesecuritydescriptor.md">FltFreeSecurityDescriptor</a>
</dt>
<dt>
<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlcreatesecuritydescriptor.md">RtlCreateSecurityDescriptor</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlcreatesecuritydescriptorrelative.md">RtlCreateSecurityDescriptorRelative</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltBuildDefaultSecurityDescriptor function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

