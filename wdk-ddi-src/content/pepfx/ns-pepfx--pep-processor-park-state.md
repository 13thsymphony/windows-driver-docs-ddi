---
UID: NS.pepfx._PEP_PROCESSOR_PARK_STATE
title: PEP_PROCESSOR_PARK_STATE
author: windows-driver-content
description: The PEP_PROCESSOR_PARK_STATE structure describes the parking state for a single processor.
old-location: kernel\pep_processor_park_state.htm
old-project: kernel
ms.assetid: 7F0BD23A-A375-43D5-B106-31E206DB6EC4
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PEP_PROCESSOR_PARK_STATE, PEP_PROCESSOR_PARK_STATE, *PPEP_PROCESSOR_PARK_STATE
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
req.alt-api: PEP_PROCESSOR_PARK_STATE
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
req.iface: 
---

# PEP_PROCESSOR_PARK_STATE structure



## -description
<p>The <b>PEP_PROCESSOR_PARK_STATE</b> structure describes the parking state for a single processor.</p>


## -syntax

````
typedef struct _PEP_PROCESSOR_PARK_STATE {
  PEPHANDLE Processor;
  BOOLEAN   Parked;
  UCHAR     Reserved[3];
} PEP_PROCESSOR_PARK_STATE, *PPEP_PROCESSOR_PARK_STATE;
````


## -struct-fields
<dl>

### -field Processor

<dd>
<p>Specifies the <b>PEPHANDLE</b> associated with this processor.</p>
</dd>

### -field Parked

<dd>
<p>Specifies whether or not this processor is parked.</p>
</dd>

### -field Reserved

<dd>
<p>This member is reserved and should be set to zero.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 10.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/mt186768">PEP_NOTIFY_PPM_PARK_MASK notification</a>
</dt>
<dt>
<a href="..\pepfx\ns-pepfx--pep-ppm-park-mask.md">PEP_PPM_PARK_MASK</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PROCESSOR_PARK_STATE structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
