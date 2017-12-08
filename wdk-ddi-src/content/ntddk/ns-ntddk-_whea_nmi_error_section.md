---
UID: NS.NTDDK._WHEA_NMI_ERROR_SECTION
title: _WHEA_NMI_ERROR_SECTION
author: windows-driver-content
description: The WHEA_NMI_ERROR_SECTION structure describes nonmaskable interrupt (NMI) error data.
old-location: whea\whea_nmi_error_section.htm
old-project: whea
ms.assetid: 960186a4-09ca-4636-b704-166137da6113
ms.author: windowsdriverdev
ms.date: 12/5/2017
ms.keywords: _WHEA_NMI_ERROR_SECTION, *PWHEA_NMI_ERROR_SECTION, WHEA_NMI_ERROR_SECTION
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
req.alt-api: WHEA_NMI_ERROR_SECTION
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

# _WHEA_NMI_ERROR_SECTION structure



## -description
The WHEA_NMI_ERROR_SECTION structure describes nonmaskable interrupt (NMI) error data.


## -syntax

````
typedef struct _WHEA_NMI_ERROR_SECTION {
  UCHAR                        Data[8];
  WHEA_NMI_ERROR_SECTION_FLAGS Flags;
} WHEA_NMI_ERROR_SECTION, *PWHEA_NMI_ERROR_SECTION;
````


## -struct-fields

### -field Data

An 8-byte data buffer that contains the data that was read from the NMI I/O ports by the NMI low-level hardware error handler (LLHEH).

### -field Flags

A WHEA_NMI_ERROR__SECTION_FLAGS union that describes the source of the NMI error. The WHEA_NMI_ERROR_FLAGS union is defined as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef union _WHEA_NMI_ERROR_SECTION_FLAGS {
  struct {
    ULONG  HypervisorError:1;
    ULONG  Reserved:31;
  };
  ULONG  AsULONG;
} WHEA_NMI_ERROR_SECTION_FLAGS, *PWHEA_NMI_ERROR_SECTION_FLAGS;</pre>
</td>
</tr>
</table></span></div>


### -field HypervisorError

A hypervisor error has occurred.

### -field Reserved

Reserved for system use.

### -field AsULONG

A ULONG representation of the contents of the WHEA_NMI_ERROR_SECTION_FLAGS union.
</dd>
</dl>

## -remarks
The WHEA_NMI_ERROR_SECTION structure describes the error data contained in a nonmaskable interrupt (NMI) error section of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. An error record contains an NMI error section only if the <b>SectionType </b>member of one of the <a href="whea.whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe the error record sections for that error record contains NMI_SECTION_GUID.

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
<a href="whea.whea_error_packet">WHEA_ERROR_PACKET</a>
</dt>
<dt>
<a href="whea.whea_error_record_section_descriptor">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_NMI_ERROR_SECTION structure%20 RELEASE:%20(12/5/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
