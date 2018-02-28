---
UID: NS:ntddk._WHEA_PROCESSOR_FAMILY_INFO
title: "_WHEA_PROCESSOR_FAMILY_INFO"
author: windows-driver-content
description: The WHEA_PROCESSOR_FAMILY_INFO union describes the processor family information for an x86 or x64 processor.
old-location: whea\whea_processor_family_info.htm
old-project: whea
ms.assetid: cc20c2d6-c76b-4f72-9762-23b9aa5fe946
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_PROCESSOR_FAMILY_INFO, PWHEA_PROCESSOR_FAMILY_INFO, PWHEA_PROCESSOR_FAMILY_INFO union pointer [WHEA Drivers and Applications], WHEA_PROCESSOR_FAMILY_INFO, WHEA_PROCESSOR_FAMILY_INFO union [WHEA Drivers and Applications], _WHEA_PROCESSOR_FAMILY_INFO, ntddk/PWHEA_PROCESSOR_FAMILY_INFO, ntddk/WHEA_PROCESSOR_FAMILY_INFO, whea.whea_processor_family_info, whearef_f15c7bb5-aee5-4a59-9869-285828d92b5e.xml"
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
-	WHEA_PROCESSOR_FAMILY_INFO
product: Windows
targetos: Windows
req.typenames: WHEA_PROCESSOR_FAMILY_INFO, *PWHEA_PROCESSOR_FAMILY_INFO
---

# _WHEA_PROCESSOR_FAMILY_INFO structure
The WHEA_PROCESSOR_FAMILY_INFO union describes the processor family information for an x86 or x64 processor.

## Syntax
````
typedef union _WHEA_PROCESSOR_FAMILY_INFO {
  struct {
    ULONG Stepping  :4;
    ULONG Model  :4;
    ULONG Family  :4;
    ULONG ProcessorType  :2;
    ULONG Reserved1  :2;
    ULONG ExtendedModel  :4;
    ULONG ExtendedFamily  :8;
    ULONG Reserved2  :4;
    ULONG Reserved3;
  };
  ULONGLONG AsULONGLONG;
} WHEA_PROCESSOR_FAMILY_INFO, *PWHEA_PROCESSOR_FAMILY_INFO;
````

## Members


`AsULONGLONG`

A ULONGLONG representation of the contents of the WHEA_PROCESSOR_FAMILY_INFO union.

`DUMMYSTRUCTNAME`



## Remarks
For x86 and x64 processors, the <b>CPUVersion</b> member of the <a href="..\ntddk\ns-ntddk-_whea_processor_generic_error_section.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure contains a WHEA_PROCESSOR_FAMILY_INFO union.

The contents of this union are obtained by executing the CPUID instruction with the EAX register set to 1 on input. For more information about the CPUID instruction, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=78804">Intel 64 and IA-32 Architectures Software Developer's Manual</a>. For additional information about the data that is contained in the members of this union, see <a href="http://go.microsoft.com/fwlink/p/?linkid=80097">AP-485 Intel Processor Identification and the CPUID Instruction</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows. |
| **Header** | ntddk.h (include Ntddk.h) |

## See Also

<a href="..\ntddk\ns-ntddk-_whea_processor_generic_error_section.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_PROCESSOR_FAMILY_INFO union%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>