---
UID: NS.PEPFX._PEP_SOC_SUBSYSTEM_METADATA
title: _PEP_SOC_SUBSYSTEM_METADATA
author: windows-driver-content
description: The PEP_SOC_SUBSYSTEM_METADATA structure contains key-value pairs that contain metadata for a system on a chip (SoC) subsystem. It is used in the context of a PEP_DPM_QUERY_SOC_SUBSYSTEM_METADATA notification sent to a platform extension plug-in (PEP).
old-location: kernel\pep_soc_subsystem_metadata.htm
old-project: kernel
ms.assetid: 4FAE15C7-7B2F-47A5-B429-B7FF7D3D018C
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _PEP_SOC_SUBSYSTEM_METADATA, PEP_SOC_SUBSYSTEM_METADATA, *PPEP_SOC_SUBSYSTEM_METADATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_SOC_SUBSYSTEM_METADATA
req.alt-loc: pepfx.h
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

# _PEP_SOC_SUBSYSTEM_METADATA structure



## -description
The <b>PEP_SOC_SUBSYSTEM_METADATA</b> structure contains key-value pairs that contain metadata for a system on a chip (SoC) subsystem. It is used in the context of a <a href="kernel.pep_dpm_query_soc_subsystem_metadata">PEP_DPM_QUERY_SOC_SUBSYSTEM_METADATA</a> notification sent to a platform extension plug-in (PEP).



## -syntax

````
typedef struct _PEP_SOC_SUBSYSTEM_METADATA {
  UNICODE_STRING Key;
  UNICODE_STRING Value;
} PEP_SOC_SUBSYSTEM_METADATA, *PPEP_SOC_SUBSYSTEM_METADATA;
````


## -struct-fields

### -field Key

[in/out]  A buffer for the PEP to write the key portion of the metadata string-pair.  <b>Key</b> must be unique among all <b>Key</b> values reported by this subsystem.  



Prior to entry into the notification callback routine, the kernel will:

<ul>
<li>Pre-allocate 64 <b>WCHARs</b> for <b>Key.Buffer[]</b></li>
<li>Zero the buffer </li>
<li>Set <b>Key.MaximumLength</b> to the size of the buffer in bytes, and </li>
<li>Set <b>Key.Length</b> = <b>0</b></li>
</ul>
Prior to exit from the callback routine, the PEP must copy a null-terminated string into <b>Key.Buffer</b> and update <b>Key.Length</b> with a byte count that is <b>sizeof(WCHAR)</b> times the number of UNICODE characters copied, not including the terminating <b>UNICODE_NULL</b>.  

The PEP must use the allocated memory that is pointed to by the address in <b>Key.Buffer</b> to provide the key. 
Since this memory is pre-allocated, its size cannot be changed. The PEP is responsible for truncating the key string, if necessary, so that it does not exceed the length specified in <b>Key.MaximumLength</b> (including the terminating <b>UNICODE_NULL</b> character).


### -field Value

[in/out] A buffer for the PEP to write the value portion of the metadata string-pair.  

Prior to entry into the notification callback routine, the kernel will:

<ul>
<li>Pre-allocate 64 <b>WCHARs</b> for <b>Value.Buffer[]</b></li>
<li>Zero the buffer </li>
<li>Set <b>Value.MaximumLength</b> to the size of the buffer in bytes, and </li>
<li>Set <b>Value.Length</b> = <b>0</b></li>
</ul>
Prior to exit from the callback routine, the PEP must copy a null-terminated string into <b>Value.Buffer</b> and update <b>Value.Length</b> with a byte count that is <b>sizeof(WCHAR)</b> times the number of UNICODE characters copied, not including the terminating <b>UNICODE_NULL</b>.  

The PEP must use the allocated memory that is pointed to by the address in <b>Value.Buffer</b> to provide the metadata value. 
Since this memory is pre-allocated, its size cannot be changed. The PEP is responsible for truncating the value string, if necessary, so that it does not exceed the length specified in <b>Value.MaximumLength</b> (including the terminating <b>UNICODE_NULL</b> character).


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with Windows 10.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Pepfx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.pep_dpm_query_soc_subsystem_metadata">PEP_DPM_QUERY_SOC_SUBSYSTEM_METADATA</a>
</dt>
<dt>
<a href="kernel.pep_query_soc_subsystem_metadata">PEP_QUERY_SOC_SUBSYSTEM_METADATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_SOC_SUBSYSTEM_METADATA structure%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

