---
UID: NS.ntddk._WHEA_XPF_PROCINFO
title: WHEA_XPF_PROCINFO
author: windows-driver-content
description: The WHEA_XPF_PROCINFO structure describes processor error information that is specific to the x86 and x64 processor architectures.
old-location: whea\whea_xpf_procinfo.htm
old-project: whea
ms.assetid: 90fb54dd-a2df-423c-8dd6-bd99c5ad1de4
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WHEA_XPF_PROCINFO, WHEA_XPF_PROCINFO, *PWHEA_XPF_PROCINFO
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
req.alt-api: WHEA_XPF_PROCINFO
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

# WHEA_XPF_PROCINFO structure



## -description
<p>The WHEA_XPF_PROCINFO structure describes processor error information that is specific to the x86 and x64 processor architectures.</p>


## -syntax

````
typedef struct _WHEA_XPF_PROCINFO {
  GUID                        CheckInfoId;
  WHEA_XPF_PROCINFO_VALIDBITS ValidBits;
  union {
    WHEA_XPF_CACHE_CHECK CacheCheck;
    WHEA_XPF_TLB_CHECK   TlbCheck;
    WHEA_XPF_BUS_CHECK   BusCheck;
    WHEA_XPF_MS_CHECK    MsCheck;
    ULONGLONG            AsULONGLONG;
  } CheckInfo;
  ULONGLONG                   TargetId;
  ULONGLONG                   RequesterId;
  ULONGLONG                   ResponderId;
  ULONGLONG                   InstructionPointer;
} WHEA_XPF_PROCINFO, *PWHEA_XPF_PROCINFO;
````


## -struct-fields
<dl>

### -field <b>CheckInfoId</b>

<dd>
<p>A GUID that identifies the processor error information that is contained in the <b>CheckInfo</b> member. The following are the possible GUIDs that can be specified for this member:</p>
<p></p>
<dl>

### -field <a id="WHEA_CACHECHECK_GUID"></a><a id="whea_cachecheck_guid"></a>WHEA_CACHECHECK_GUID

<dd>
<p>The <b>CheckInfo.CacheCheck</b> member contains cache error information.</p>
</dd>

### -field <a id="WHEA_TLBCHECK_GUID"></a><a id="whea_tlbcheck_guid"></a>WHEA_TLBCHECK_GUID

<dd>
<p>The <b>CheckInfo.TlbCheck</b> member contains translation lookaside buffer error information.</p>
</dd>

### -field <a id="WHEA_BUSCHECK_GUID"></a><a id="whea_buscheck_guid"></a>WHEA_BUSCHECK_GUID

<dd>
<p>The <b>CheckInfo.BusCheck</b> member contains bus error information.</p>
</dd>

### -field <a id="WHEA_MSCHECK_GUID"></a><a id="whea_mscheck_guid"></a>WHEA_MSCHECK_GUID

<dd>
<p>The <b>CheckInfo.MsCheck</b> member contains microarchitecture-specific error information.</p>
</dd>
</dl>
</dd>

### -field <b>ValidBits</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560663">WHEA_XPF_PROCINFO_VALIDBITS</a> union that specifies which members of this structure contain valid data.</p>
</dd>

### -field <b>CheckInfo</b>

<dd>
<p>A union of unions that are specific to each different type of processor error information.</p>
<p>This member contains valid data only if the <b>ValidBits.CheckInfo</b> bit is set.

</p>
<dl>

### -field <b>CacheCheck</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560642">WHEA_XPF_CACHE_CHECK</a> union that describes cache error information. </p>
</dd>

### -field <b>TlbCheck</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560665">WHEA_XPF_TLB_CHECK</a> union that describes translation lookaside buffer error information. </p>
</dd>

### -field <b>BusCheck</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560639">WHEA_XPF_BUS_CHECK</a> union that describes bus error information.</p>
</dd>

### -field <b>MsCheck</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff560652">WHEA_XPF_MS_CHECK</a> union that describes microarchitecture-specific error information. </p>
</dd>

### -field <b>AsULONGLONG</b>

<dd>
<p>A ULONGLONG representation of the contents of the <b>CheckInfo</b> union.</p>
</dd>
</dl>
</dd>

### -field <b>TargetId</b>

<dd>
<p>An identifier that uniquely identifies the target associated with the error.</p>
<p>This member contains valid data only if the <b>ValidBits.TargetId</b> bit is set.</p>
</dd>

### -field <b>RequesterId</b>

<dd>
<p>An identifier that uniquely identifies the requester associated with the error.</p>
<p>This member contains valid data only if the <b>ValidBits.RequesterId</b> bit is set.</p>
</dd>

### -field <b>ResponderId</b>

<dd>
<p>An identifier that uniquely identifies the responder associated with the error.</p>
<p>This member contains valid data only if the <b>ValidBits.Responder</b> bit is set.</p>
</dd>

### -field <b>InstructionPointer</b>

<dd>
<p>The instruction pointer at the time that the error occurred.</p>
<p>This member contains valid data only if the <b>ValidBits.InstructionPointer</b> bit is set.</p>
</dd>
</dl>

## -remarks
<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560655">WHEA_XPF_PROCESSOR_ERROR_SECTION</a> structure contains an array of WHEA_XPF_PROCINFO structures, each of which describes specific error information associated with the processor error that occurred.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560639">WHEA_XPF_BUS_CHECK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560642">WHEA_XPF_CACHE_CHECK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560652">WHEA_XPF_MS_CHECK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560655">WHEA_XPF_PROCESSOR_ERROR_SECTION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560663">WHEA_XPF_PROCINFO_VALIDBITS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560665">WHEA_XPF_TLB_CHECK</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_XPF_PROCINFO structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
