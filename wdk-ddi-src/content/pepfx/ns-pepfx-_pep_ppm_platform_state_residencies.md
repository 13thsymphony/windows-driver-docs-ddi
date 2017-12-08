---
UID: NS.PEPFX._PEP_PPM_PLATFORM_STATE_RESIDENCIES
title: _PEP_PPM_PLATFORM_STATE_RESIDENCIES
author: windows-driver-content
description: The PEP_PPM_PLATFORM_STATE_RESIDENCIES structure contains the accumulated residency times and transition counts for the idle states that are supported by the hardware platform.
old-location: kernel\pep_ppm_platform_state_residencies.htm
old-project: kernel
ms.assetid: 5B6186EB-EC08-4C11-9CCF-E07D78FBD535
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _PEP_PPM_PLATFORM_STATE_RESIDENCIES, *PPEP_PPM_PLATFORM_STATE_RESIDENCIES, PEP_PPM_PLATFORM_STATE_RESIDENCIES
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
req.alt-api: PEP_PPM_PLATFORM_STATE_RESIDENCIES
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

# _PEP_PPM_PLATFORM_STATE_RESIDENCIES structure



## -description
The <b>PEP_PPM_PLATFORM_STATE_RESIDENCIES</b> structure contains the accumulated residency times and transition counts for the idle states that are supported by the hardware platform.


## -syntax

````
typedef struct _PEP_PPM_PLATFORM_STATE_RESIDENCIES {
  ULONG                             Count;
  PPEP_PPM_PLATFORM_STATE_RESIDENCY States;
} PEP_PPM_PLATFORM_STATE_RESIDENCIES, *PPEP_PPM_PLATFORM_STATE_RESIDENCIES;
````


## -struct-fields

### -field Count

[in] The number of elements in the array pointed to by the <b>States</b> member. The number of array elements equals the number of platform idle states that the PEP previously provided in response to a <a href="kernel.pep_notify_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification.

### -field States

[in] A pointer to an output buffer to which the PEP writes an array of <a href="kernel.pep_ppm_platform_state_residency">PEP_PPM_PLATFORM_STATE_RESIDENCY</a> structures. Each structure contains the accumulated residency and transition count information for a particular platform idle state. This buffer is guaranteed to be large enough to contain the number of array elements specified by the <b>Count</b> member. Each idle state is identified by its array index. If the array contains N elements, idle state indexes range from 0 to N-1.

## -remarks
This structure is used by the <a href="kernel.pep_notify_ppm_query_platform_state_residencies">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE_RESIDENCIES</a> notification. Both members of the structure contain input values that the Windows <a href="kernel.power_management_framework__pofx__routines">power management framework</a> (PoFx) supplies when this notification is sent to the PEP. PoFx allocates the output buffer pointed to by the <b>States</b> member, and the PEP writes to this buffer.

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
<a href="kernel.pep_notify_ppm_query_platform_state_residencies">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE_RESIDENCIES</a>
</dt>
<dt>
<a href="kernel.pep_notify_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>
</dt>
<dt>
<a href="kernel.pep_ppm_platform_state_residency">PEP_PPM_PLATFORM_STATE_RESIDENCY</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_PLATFORM_STATE_RESIDENCIES structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
