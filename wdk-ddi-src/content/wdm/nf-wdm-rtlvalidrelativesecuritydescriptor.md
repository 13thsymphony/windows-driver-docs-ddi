---
UID: NF:wdm.RtlValidRelativeSecurityDescriptor
title: RtlValidRelativeSecurityDescriptor function
author: windows-driver-content
description: The RtlValidRelativeSecurityDescriptor routine checks the validity of a self-relative security descriptor.
old-location: kernel\rtlvalidrelativesecuritydescriptor.htm
old-project: kernel
ms.assetid: 1fb993f0-4289-4406-8a56-47b12c73f4e6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlValidRelativeSecurityDescriptor, RtlValidRelativeSecurityDescriptor routine [Kernel-Mode Driver Architecture], k109_b261fb47-147f-4e39-81fb-bdbc31d53681.xml, kernel.rtlvalidrelativesecuritydescriptor, wdm/RtlValidRelativeSecurityDescriptor
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
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlValidRelativeSecurityDescriptor
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlValidRelativeSecurityDescriptor function
The <b>RtlValidRelativeSecurityDescriptor</b> routine checks the validity of a self-relative security descriptor.

## Syntax

````
BOOLEAN RtlValidRelativeSecurityDescriptor(
  _In_ PSECURITY_DESCRIPTOR SecurityDescriptorInput,
  _In_ ULONG                SecurityDescriptorLength,
  _In_ SECURITY_INFORMATION RequiredInformation
);
````

## Parameters

`SecurityDescriptorInput`

A pointer to the buffer that contains the security descriptor in self-relative format. The buffer must begin with a <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> structure, which is followed by the rest of the security descriptor data.

`SecurityDescriptorLength`

The size of the <i>SecurityDescriptorInput</i> structure.

`RequiredInformation`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a> value that specifies the information that is required to be contained in the security descriptor.


## Return Value

<b>RtlValidRelativeSecurityDescriptor</b> returns <b>TRUE</b> if the security descriptor is valid and includes the information that the <i>RequiredInformation</i> parameter specifies. Otherwise, this routine returns <b>FALSE</b>.

## Remarks

To check the validity of a security descriptor in absolute format, use <a href="..\wdm\nf-wdm-rtlvalidsecuritydescriptor.md">RtlValidSecurityDescriptor</a> instead.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a>



<a href="..\wdm\nf-wdm-rtlvalidsecuritydescriptor.md">RtlValidSecurityDescriptor</a>



<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlValidRelativeSecurityDescriptor routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>