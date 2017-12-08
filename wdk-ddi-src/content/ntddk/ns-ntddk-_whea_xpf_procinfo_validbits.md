---
UID: NS.NTDDK._WHEA_XPF_PROCINFO_VALIDBITS
title: _WHEA_XPF_PROCINFO_VALIDBITS
author: windows-driver-content
description: The WHEA_XPF_PROCINFO_VALIDBITS union describes which members of a WHEA_XPF_PROCINFO structure contain valid data.
old-location: whea\whea_xpf_procinfo_validbits.htm
old-project: whea
ms.assetid: ca0eef79-d990-4a82-b2d6-a51e3790cfc2
ms.author: windowsdriverdev
ms.date: 12/5/2017
ms.keywords: _WHEA_XPF_PROCINFO_VALIDBITS, *PWHEA_XPF_PROCINFO_VALIDBITS, WHEA_XPF_PROCINFO_VALIDBITS
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
req.alt-api: WHEA_XPF_PROCINFO_VALIDBITS
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

# _WHEA_XPF_PROCINFO_VALIDBITS structure



## -description
The WHEA_XPF_PROCINFO_VALIDBITS union describes which members of a <a href="whea.whea_xpf_procinfo">WHEA_XPF_PROCINFO</a> structure contain valid data.


## -syntax

````
typedef union _WHEA_XPF_PROCINFO_VALIDBITS {
  struct {
    ULONGLONG CheckInfo  :1;
    ULONGLONG TargetId  :1;
    ULONGLONG RequesterId  :1;
    ULONGLONG ResponderId  :1;
    ULONGLONG InstructionPointer  :1;
    ULONGLONG Reserved  :59;
  };
  ULONGLONG ValidBits;
} WHEA_XPF_PROCINFO_VALIDBITS, *PWHEA_XPF_PROCINFO_VALIDBITS;
````


## -struct-fields

### -field CheckInfo

A single bit that indicates that the <b>CheckInfo</b> member of the WHEA_XPF_PROCINFO structure contains valid data.

### -field TargetId

A single bit that indicates that the <b>TargetId</b> member of the WHEA_XPF_PROCINFO structure contains valid data.

### -field RequesterId

A single bit that indicates that the <b>RequesterId</b> member of the WHEA_XPF_PROCINFO structure contains valid data.

### -field ResponderId

A single bit that indicates that the <b>ResponderId</b> member of the WHEA_XPF_PROCINFO structure contains valid data.

### -field InstructionPointer

A single bit that indicates that the <b>InstructionPointer</b> member of the WHEA_XPF_PROCINFO structure contains valid data.

### -field Reserved

Reserved for system use.

### -field ValidBits

A ULONGLONG representation of the contents of the WHEA_XPF_PROCINFO_VALIDBITS union.

## -remarks
A WHEA_XPF_PROCINFO_VALIDBITS union is contained within the <a href="whea.whea_xpf_procinfo">WHEA_XPF_PROCINFO</a> structure.

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
<a href="whea.whea_xpf_procinfo">WHEA_XPF_PROCINFO</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_XPF_PROCINFO_VALIDBITS union%20 RELEASE:%20(12/5/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
