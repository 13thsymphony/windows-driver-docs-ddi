---
UID: NS:ntddk._WHEA_XPF_PROCESSOR_ERROR_SECTION
title: "_WHEA_XPF_PROCESSOR_ERROR_SECTION"
author: windows-driver-content
description: The WHEA_XPF_PROCESSOR_ERROR_SECTION structure describes processor error data that is specific to the x86/x64 processor architecture.
old-location: whea\whea_xpf_processor_error_section.htm
old-project: whea
ms.assetid: e994c778-4a1b-4c7d-a9fb-4481d9edda0d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "*PWHEA_XPF_PROCESSOR_ERROR_SECTION, whea.whea_xpf_processor_error_section, WHEA_XPF_PROCESSOR_ERROR, ntddk/PWHEA_XPF_PROCESSOR_ERROR_SECTION, whearef_e3338334-dc16-4242-9c30-0daaab2df957.xml, WHEA_XPF_PROCESSOR_ERROR_SECTION, WHEA_XPF_PROCESSOR_ERROR_SECTION structure [WHEA Drivers and Applications], _WHEA_XPF_PROCESSOR_ERROR_SECTION, PWHEA_XPF_PROCESSOR_ERROR_SECTION structure pointer [WHEA Drivers and Applications], ntddk/WHEA_XPF_PROCESSOR_ERROR_SECTION, *PWHEA_XPF_PROCESSOR_ERROR, PWHEA_XPF_PROCESSOR_ERROR_SECTION"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	WHEA_XPF_PROCESSOR_ERROR_SECTION
product: Windows
targetos: Windows
req.typenames: "*PWHEA_XPF_PROCESSOR_ERROR_SECTION, WHEA_XPF_PROCESSOR_ERROR_SECTION"
---

# _WHEA_XPF_PROCESSOR_ERROR_SECTION structure
The WHEA_XPF_PROCESSOR_ERROR_SECTION structure describes processor error data that is specific to the x86/x64 processor architecture.

## Syntax
````
typedef struct _WHEA_XPF_PROCESSOR_ERROR_SECTION {
  WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS ValidBits;
  ULONGLONG                                  LocalAPICId;
  UCHAR                                      CpuId[48];
  UCHAR                                      VariableInfo[ANYSIZE_ARRAY];
} WHEA_XPF_PROCESSOR_ERROR_SECTION, *PWHEA_XPF_PROCESSOR_ERROR_SECTION;
````

## Members


## Remarks
The WHEA_XPF_PROCESSOR_ERROR_SECTION structure describes the error data that is contained in an x86/x64 processor error section of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. An error record contains an x86/x64 processor error section only if the <b>SectionType </b>member of one of the <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describes the error record sections for that error record contains XPF_PROCESSOR_ERROR_SECTION_GUID.

The following diagram shows how the data structures that contain the processor error data are stored in the <b>VariableInfo</b> member.
<img alt="Diagram illustrating how the data structures that contain the processor error data are stored in the VariableInfo member" src="images/wheaxpfsection.gif"/>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="..\ntddk\ns-ntddk-whea_xpf_processor_error_section_validbits.md">WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS</a>

<a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>

<a href="..\ntddk\ns-ntddk-_whea_xpf_context_info.md">WHEA_XPF_CONTEXT_INFO</a>

<a href="..\ntddk\ns-ntddk-_whea_xpf_procinfo.md">WHEA_XPF_PROCINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_XPF_PROCESSOR_ERROR_SECTION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>