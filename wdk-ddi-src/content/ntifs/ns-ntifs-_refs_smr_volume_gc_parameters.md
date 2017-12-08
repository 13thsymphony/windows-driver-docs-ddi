---
UID: NS.NTIFS._REFS_SMR_VOLUME_GC_PARAMETERS
title: _REFS_SMR_VOLUME_GC_PARAMETERS
author: windows-driver-content
description: The REFS_SMR_VOLUME_GC_PARAMETERS structure.
old-location: ifsk\refs_smr_volume_gc_parameters.htm
old-project: ifsk
ms.assetid: 78C8FFFE-8A80-4C92-B822-5C6675E2BC18
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _REFS_SMR_VOLUME_GC_PARAMETERS, REFS_SMR_VOLUME_GC_PARAMETERS, *PREFS_SMR_VOLUME_GC_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: REFS_SMR_VOLUME_GC_PARAMETERS
req.alt-loc: Ntifs.h
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
---

# _REFS_SMR_VOLUME_GC_PARAMETERS structure



## -description
The <b>REFS_SMR_VOLUME_GC_PARAMETERS</b> structure is used as the input structure for <a href="ifsk.fsctl_set_refs_smr_volume_gc_parameters">FSCTL_SET_REFS_SMR_VOLUME_GC_PARAMETERS</a>.


## -syntax

````
typedef struct _REFS_SMR_VOLUME_GC_PARAMETERS {
  ULONG                     Version;
  ULONG                     Flags;
  REFS_SMR_VOLUME_GC_ACTION Action;
  REFS_SMR_VOLUME_GC_METHOD Method;
  ULONG                     IoGranularity;
  ULONG                     CompressionFormat;
  ULONG                     Unused[8];
} REFS_SMR_VOLUME_GC_PARAMETERS, *PREFS_SMR_VOLUME_GC_PARAMETERS;
````


## -struct-fields

### -field Version

Specifies the current version of <b>REFS_SMR_VOLUME_GC_PARAMETERS</b>. Version is currently ignored but should be set to <b>REFS_SMR_VOLUME_GC_PARAMETERS_VERSION_V1</b>.

### -field Flags

Specifies the flags. Flags is currently ignored.

### -field Action

Specifies the garbage collection action.

### -field Method

Specifies the garbage collection method or strategy. Currently only <b>MsSmrGcMethodCompaction</b> is allowed.

### -field IoGranularity

Specifies the volume's granularity. <b>IoGranularity</b> is a multiple of the cluster size up to the Shingled Magnetic Recording (SMR) band size (256 MB).  Zero or non-multiple of cluster size will result in a <b>STATUS_INVALID_PARAMETERS</b> status.

### -field CompressionFormat

Reserved for future use.

### -field Unused

Reserved for future use.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available starting with Windows 10, version 1709.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fsctl_set_refs_smr_volume_gc_parameters">FSCTL_SET_REFS_SMR_VOLUME_GC_PARAMETERS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20REFS_SMR_VOLUME_GC_PARAMETERS structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
