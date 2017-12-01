---
UID: NS.ntddk._WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS
title: WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS
author: windows-driver-content
description: The WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contain valid data.
old-location: whea\whea_processor_generic_error_section_validbits.htm
old-project: whea
ms.assetid: f7173767-a177-4a79-917b-41acc9eff758
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS,
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
req.alt-api: WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS
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
req.iface: 
---

# WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS structure



## -description
<p>The WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union describes which members of a <a href="..\ntddk\ns-ntddk--whea-processor-generic-error-section.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure contain valid data.</p>


## -syntax

````
typedef union _WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS {
  struct {
    ULONGLONG ProcessorType  :1;
    ULONGLONG InstructionSet  :1;
    ULONGLONG ErrorType  :1;
    ULONGLONG Operation  :1;
    ULONGLONG Flags  :1;
    ULONGLONG Level  :1;
    ULONGLONG CPUVersion  :1;
    ULONGLONG CPUBrandString  :1;
    ULONGLONG ProcessorId  :1;
    ULONGLONG TargetAddress  :1;
    ULONGLONG RequesterId  :1;
    ULONGLONG ResponderId  :1;
    ULONGLONG InstructionPointer  :1;
    ULONGLONG Reserved  :51;
  };
  ULONGLONG ValidBits;
} WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS, *PWHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS;
````


## -struct-fields
<dl>

### -field <b>ProcessorType</b>

<dd>
<p>A single bit that indicates that the <b>ProcessorType</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.</p>
</dd>

### -field <b>InstructionSet</b>

<dd>
<p>A single bit that indicates that the <b>InstructionSet</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.</p>
</dd>

### -field <b>ErrorType</b>

<dd>
<p>A single bit that indicates that the <b>ErrorType</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.</p>
</dd>

### -field <b>Operation</b>

<dd>
<p>A single bit that indicates that the <b>Operation</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>A single bit that indicates that the <b>Flags</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.</p>
</dd>

### -field <b>Level</b>

<dd>
<p>A single bit that indicates that the <b>Level</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.</p>
</dd>

### -field <b>CPUVersion</b>

<dd>
<p>A single bit that indicates that the <b>CPUVersion</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.</p>
</dd>

### -field <b>CPUBrandString</b>

<dd>
<p>A single bit that indicates that the <b>CPUBrandString</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.</p>
</dd>

### -field <b>ProcessorId</b>

<dd>
<p>A single bit that indicates that the <b>ProcessorId</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.</p>
</dd>

### -field <b>TargetAddress</b>

<dd>
<p>A single bit that indicates that the <b>TargetAddress</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.</p>
</dd>

### -field <b>RequesterId</b>

<dd>
<p>A single bit that indicates that the <b>RequesterId</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.</p>
</dd>

### -field <b>ResponderId</b>

<dd>
<p>A single bit that indicates that the <b>ResponderId</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.</p>
</dd>

### -field <b>InstructionPointer</b>

<dd>
<p>A single bit that indicates that the <b>InstructionPointer</b> member of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION structure contains valid data.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Reserved for system use.</p>
</dd>

### -field <b>ValidBits</b>

<dd>
<p>A ULONGLONG representation of the contents of the WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union.</p>
</dd>
</dl>

## -remarks
<p>A WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union is contained within the <a href="..\ntddk\ns-ntddk--whea-processor-generic-error-section.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\ntddk\ns-ntddk--whea-processor-generic-error-section.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_PROCESSOR_GENERIC_ERROR_SECTION_VALIDBITS union%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
