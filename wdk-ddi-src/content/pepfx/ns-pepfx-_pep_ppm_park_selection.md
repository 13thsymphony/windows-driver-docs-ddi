---
UID: NS.PEPFX._PEP_PPM_PARK_SELECTION
title: _PEP_PPM_PARK_SELECTION
author: windows-driver-content
description: The PEP_PPM_PARK_SELECTION structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding which processors in the platform should be parked to reduce power consumption.
old-location: kernel\pep_ppm_park_selection.htm
old-project: kernel
ms.assetid: 1957D03D-7C85-4A58-A5CC-94D3C9913F5A
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _PEP_PPM_PARK_SELECTION, *PPEP_PPM_PARK_SELECTION, PEP_PPM_PARK_SELECTION
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
req.alt-api: PEP_PPM_PARK_SELECTION
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

# _PEP_PPM_PARK_SELECTION structure



## -description
The <b>PEP_PPM_PARK_SELECTION</b> structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding which processors in the platform should be parked to reduce power consumption.


## -syntax

````
typedef struct _PEP_PPM_PARK_SELECTION {
  ULONG                          AdditionalUnparkedProcessors;
  ULONG                          Count;
  PPEP_PROCESSOR_PARK_PREFERENCE Processors;
} PEP_PPM_PARK_SELECTION, *PPEP_PPM_PARK_SELECTION;
````


## -struct-fields

### -field AdditionalUnparkedProcessors

[in] The number of additional processors that need to be parked.
This number includes all processors in the <b>Processors</b> array for which the PEP sets <b>PepPreference</b> to PROCESSOR_PARK_PREFERENCE_PARKED but the operating system sets <b>PoPreference</b> to either PROCESSOR_PARK_PREFERENCE_UNPARKED or PROCESSOR_PARK_PREFERENCE_NONE. For more information about these values, see <a href="kernel.pep_processor_park_preference">PEP_PROCESSOR_PARK_PREFERENCE</a>.
This number does <u>not</u> include processors in the <b>Processors</b> array for which the operating system sets the <b>PoPreference</b> value to PROCESSOR_PARK_PREFERENCE_PARKED.

### -field Count

[in] The number of elements in the array pointed to by the <b>Processors</b> member.

### -field Processors

[in/out] A pointer to an array of <a href="kernel.pep_processor_park_preference">PEP_PROCESSOR_PARK_PREFERENCE</a> structures. The <b>Count</b> member specifies the number of elements in the array.


### -field On input

Each array element indicates the parking preferences for a particular processor.

### -field On output

Returns the PEP parking preference for each processor.
</dd>
</dl>
The Processors array is guaranteed to contain the processors in increasing order by processor index.

## -remarks
This structure is used by the <a href="kernel.pep_notify_ppm_park_selection">PEP_NOTIFY_PPM_PARK_SELECTION</a> notification. All three members of the structure contain input values that are set by the Windows <a href="kernel.power_management_framework__pofx__routines">power management framework</a> (PoFx) before this notification is sent to the PEP.

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
<a href="kernel.pep_notify_ppm_park_selection">PEP_NOTIFY_PPM_PARK_SELECTION</a>
</dt>
<dt>
<a href="kernel.pep_processor_park_preference">PEP_PROCESSOR_PARK_PREFERENCE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_PARK_SELECTION structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
