---
UID: NF:fltkernel.FltBuildDefaultSecurityDescriptor
title: FltBuildDefaultSecurityDescriptor function
author: windows-driver-content
description: FltBuildDefaultSecurityDescriptor builds a default security descriptor for use with FltCreateCommunicationPort.
old-location: ifsk\fltbuilddefaultsecuritydescriptor.htm
old-project: ifsk
ms.assetid: 0e886c08-38dd-4960-9b79-4c6e68ac488d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_a_to_d_5b763c42-6bea-4c52-8148-60c18a2f2aeb.xml, FltBuildDefaultSecurityDescriptor, FltBuildDefaultSecurityDescriptor function [Installable File System Drivers], fltkernel/FltBuildDefaultSecurityDescriptor, ifsk.fltbuilddefaultsecuritydescriptor
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltBuildDefaultSecurityDescriptor
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltBuildDefaultSecurityDescriptor function
<b>FltBuildDefaultSecurityDescriptor</b> builds a default security descriptor for use with <a href="..\fltkernel\nf-fltkernel-fltcreatecommunicationport.md">FltCreateCommunicationPort</a>.

## Syntax

````
NTSTATUS FltBuildDefaultSecurityDescriptor(
  _Out_ PSECURITY_DESCRIPTOR *SecurityDescriptor,
  _In_  ACCESS_MASK          DesiredAccess
);
````

## Parameters

`SecurityDescriptor`

Pointer to a caller-allocated variable that receives an opaque pointer to the newly created <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>.

`DesiredAccess`

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


## Return Value

<b>FltBuildDefaultSecurityDescriptor</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltBuildDefaultSecurityDescriptor</b> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
</table>

## Remarks

When creating a minifilter driver communication port, a minifilter driver can call <b>FltBuildDefaultSecurityDescriptor</b> to create a default security descriptor for the port. The minifilter driver then creates the port by calling <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> and <a href="..\fltkernel\nf-fltkernel-fltcreatecommunicationport.md">FltCreateCommunicationPort</a>. The security descriptor is passed as a parameter to <b>InitializeObjectAttributes</b>. 

<b>FltBuildDefaultSecurityDescriptor</b> causes the system to allocate a default security descriptor from paged pool. When this security descriptor is applied to an object, only users with system or administrator privileges have access to the object. 

Minifilter drivers usually call <b>FltBuildDefaultSecurityDescriptor</b> immediately before calling <a href="..\fltkernel\nf-fltkernel-fltcreatecommunicationport.md">FltCreateCommunicationPort</a> and <a href="..\fltkernel\nf-fltkernel-fltfreesecuritydescriptor.md">FltFreeSecurityDescriptor</a> immediately after calling <b>FltCreateCommunicationPort</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>



<a href="..\ntifs\nf-ntifs-rtlcreatesecuritydescriptorrelative.md">RtlCreateSecurityDescriptorRelative</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>



<a href="..\wdm\nf-wdm-rtlcreatesecuritydescriptor.md">RtlCreateSecurityDescriptor</a>



<a href="..\fltkernel\nf-fltkernel-fltfreesecuritydescriptor.md">FltFreeSecurityDescriptor</a>



<a href="..\fltkernel\nf-fltkernel-fltcreatecommunicationport.md">FltCreateCommunicationPort</a>