---
UID : NF:wdm.RtlCreateSecurityDescriptor
title : RtlCreateSecurityDescriptor function
author : windows-driver-content
description : The RtlCreateSecurityDescriptor routine initializes a new absolute-format security descriptor. On return, the security descriptor is initialized with no system ACL, no discretionary ACL, no owner, no primary group, and all control flags set to zero.
old-location : kernel\rtlcreatesecuritydescriptor.htm
old-project : kernel
ms.assetid : f9e08a57-c9dd-4703-b29d-c169ba77f194
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlCreateSecurityDescriptor routine [Kernel-Mode Driver Architecture], RtlCreateSecurityDescriptor, k109_3e7817b3-76e0-4acb-b8a3-af78219ffb85.xml, wdm/RtlCreateSecurityDescriptor, kernel.rtlcreatesecuritydescriptor
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# RtlCreateSecurityDescriptor function
The <b>RtlCreateSecurityDescriptor</b> routine initializes a new absolute-format security descriptor. On return, the security descriptor is initialized with no system ACL, no discretionary ACL, no owner, no primary group, and all control flags set to zero.

## Syntax

````
NTSTATUS RtlCreateSecurityDescriptor(
  _Out_ PSECURITY_DESCRIPTOR SecurityDescriptor,
  _In_  ULONG                Revision
);
````

## Parameters

`SecurityDescriptor`

Pointer to the buffer for the <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> to be initialized.

`Revision`

Specifies the revision level to assign to the security descriptor. Set this parameter to SECURITY_DESCRIPTOR_REVISION.


## Return Value

<b>RtlCreateSecurityDescriptor</b> can return one of the following.
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
The caller specified an unsupported value  for <i>Revision</i>.

</td>
</tr>
</table>

## Remarks

A successful call to this routine initializes a security descriptor. The fields in this descriptor are set to initial values that indicate that there are no security constraints.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of Windows. Available in Windows 2000 and later versions of Windows. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe (kernel mode); Ntdll.dll (user mode) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wdm\nf-wdm-rtlsetdaclsecuritydescriptor.md">RtlSetDaclSecurityDescriptor</a>

<a href="..\wdm\nf-wdm-rtllengthsecuritydescriptor.md">RtlLengthSecurityDescriptor</a>

<a href="..\wdm\nf-wdm-rtlvalidsecuritydescriptor.md">RtlValidSecurityDescriptor</a>

<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlCreateSecurityDescriptor routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>