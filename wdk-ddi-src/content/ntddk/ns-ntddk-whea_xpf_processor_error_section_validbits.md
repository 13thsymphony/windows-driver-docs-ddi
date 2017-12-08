---
UID: NS.NTDDK.WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS
title: WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS
author: windows-driver-content
description: The WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_XPF_PROCESSOR_ERROR_SECTION structure contain valid data and the number of structures that are contained in the WHEA_XPF_PROCESSOR_ERROR_SECTION structure's VariableInfo member.
old-location: whea\whea_xpf_processor_error_section_validbits.htm
old-project: whea
ms.assetid: f6b18ffa-f784-4382-9861-4d92e2071ebf
ms.author: windowsdriverdev
ms.date: 12/5/2017
ms.keywords: WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS, *PWHEA_XPF_PROCESSOR_ERROR_VALIDBITS, WHEA_XPF_PROCESSOR_ERROR_VALIDBITS
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
req.alt-api: WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS
req.alt-loc: ntddk.h
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
---

# WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS structure



## -description
The WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union describes which members of a <a href="..\ntddk\ns-ntddk-whea_xpf_processor_error_section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a> structure contain valid data and the number of structures that are contained in the WHEA_XPF_PROCESSOR_ERROR_SECTION structure's <b>VariableInfo</b> member.


## -syntax

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


## -struct-fields

### -field LocalAPICId

A single bit that indicates that the <b>LocalAPICId</b> member of the WHEA_XPF_PROCESSOR_ERROR_SECTION structure contains valid data.

### -field CpuId

A single bit that indicates that the <b>CpuId</b> member of the WHEA_XPF_PROCESSOR_ERROR_SECTION structure contains valid data.

### -field ProcInfoCount

The number of <a href="whea.whea_xpf_procinfo">WHEA_XPF_PROCINFO</a> structures that are contained in the WHEA_XPF_PROCESSOR_ERROR_SECTION structure's <b>VariableInfo</b> member.

### -field ContextInfoCount

The number of <a href="whea.whea_xpf_context_info">WHEA_XPF_CONTEXT_INFO</a> structures that are contained in the WHEA_XPF_PROCESSOR_ERROR_SECTION structure's <b>VariableInfo</b> member.

### -field Reserved

Reserved for system use.

### -field ValidBits

A ULONGLONG representation of the contents of the WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union.

## -remarks
A WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union is contained within the <a href="..\ntddk\ns-ntddk-whea_xpf_processor_error_section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a> structure.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="whea.whea_xpf_context_info">WHEA_XPF_CONTEXT_INFO</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk-whea_xpf_processor_error_section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a>
</dt>
<dt>
<a href="whea.whea_xpf_procinfo">WHEA_XPF_PROCINFO</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_XPF_PROCESSOR_ERROR_SECTION_VALIDBITS union%20 RELEASE:%20(12/5/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
