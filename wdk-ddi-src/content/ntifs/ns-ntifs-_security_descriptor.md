---
UID: NS:ntifs._SECURITY_DESCRIPTOR
title: "_SECURITY_DESCRIPTOR"
author: windows-driver-content
description: The SECURITY_DESCRIPTOR structure specifies the security information that is associated with an object. For more information, see the reference page for SECURITY_DESCRIPTOR in the Installable File System documentation.
old-location: kernel\security_descriptor.htm
old-project: kernel
ms.assetid: 0af0685c-d3a3-4c76-8fca-fb38f60411bf
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PISECURITY_DESCRIPTOR, SECURITY_DESCRIPTOR, SECURITY_DESCRIPTOR structure [Kernel-Mode Driver Architecture], _SECURITY_DESCRIPTOR, kernel.security_descriptor, kstruct_d_0b8cd06a-644b-40a4-b2bb-6c8c74d63db8.xml, wdm/SECURITY_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	SECURITY_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: SECURITY_DESCRIPTOR, *PISECURITY_DESCRIPTOR
---

# _SECURITY_DESCRIPTOR structure
The <b>SECURITY_DESCRIPTOR</b> structure specifies the security information that is associated with an object. For more information, see the reference page for <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> in the Installable File System documentation.

## Syntax


## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntifs.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="..\wdm\nf-wdm-rtllengthsecuritydescriptor.md">RtlLengthSecurityDescriptor</a>



<a href="..\wdm\nf-wdm-obgetobjectsecurity.md">ObGetObjectSecurity</a>



<a href="..\wdm\nf-wdm-obreleaseobjectsecurity.md">ObReleaseObjectSecurity</a>



<a href="..\wdm\nf-wdm-rtlsetdaclsecuritydescriptor.md">RtlSetDaclSecurityDescriptor</a>



<a href="..\wdm\nf-wdm-sedeassignsecurity.md">SeDeassignSecurity</a>



<a href="..\wdm\nf-wdm-seassignsecurity.md">SeAssignSecurity</a>



<a href="..\wdm\nf-wdm-seaccesscheck.md">SeAccessCheck</a>



<a href="..\wdm\nf-wdm-rtlvalidsecuritydescriptor.md">RtlValidSecurityDescriptor</a>



<a href="..\wdm\nf-wdm-rtlcreatesecuritydescriptor.md">RtlCreateSecurityDescriptor</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SECURITY_DESCRIPTOR structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>