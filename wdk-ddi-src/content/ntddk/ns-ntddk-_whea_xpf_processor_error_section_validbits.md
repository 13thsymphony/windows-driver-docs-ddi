---
UID: NS:ntddk._WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS
title: "_WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS"
author: windows-driver-content
description: The WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_XPF_PROCESSOR_ERROR_SECTION structure contain valid data and the number of structures that are contained in the WHEA_XPF_PROCESSOR_ERROR_SECTION structure's VariableInfo member.
old-location: whea\whea_xpf_processor_error_section_validbits.htm
old-project: whea
ms.assetid: f6b18ffa-f784-4382-9861-4d92e2071ebf
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, PWHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, PWHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union pointer [WHEA Drivers and Applications], WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union [WHEA Drivers and Applications], _WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, ntddk/PWHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, ntddk/WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, whea.whea_xpf_processor_error_section_validbits, whearef_cd965099-c110-4ff6-993e-c4ccab88cd80.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS
product: Windows
targetos: Windows
req.typenames: WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, *PWHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS
---

# _WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS structure
The WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union describes which members of a <a href="..\ntddk\ns-ntddk-_whea_xpf_processor_error_section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a> structure contain valid data and the number of structures that are contained in the WHEA_XPF_PROCESSOR_ERROR_SECTION structure's <b>VariableInfo</b> member.

## Syntax
````
typedef union _WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS {
  struct {
    ULONGLONG LocalAPICId  :1;
    ULONGLONG CpuId  :1;
    ULONGLONG ProcInfoCount  :6;
    ULONGLONG ContextInfoCount  :6;
    ULONGLONG Reserved  :50;
  };
  ULONGLONG ValidBits;
} WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, *PWHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS;
````

## Members


`DUMMYSTRUCTNAME`



`ValidBits`

A ULONGLONG representation of the contents of the WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union.

## Remarks
A WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union is contained within the <a href="..\ntddk\ns-ntddk-_whea_xpf_processor_error_section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo.md">WHEA_XPF_PROCINFO</a>



<a href="..\ntddk\ns-ntddk-_whea_xpf_processor_error_section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a>



<a href="..\ntddk\ns-ntddk-_whea_xpf_context_info.md">WHEA_XPF_CONTEXT_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>