---
UID: NS.PMI._PMI_METERED_HARDWARE_INFORMATION
title: _PMI_METERED_HARDWARE_INFORMATION
author: windows-driver-content
description: The PMI_METERED_HARDWARE_INFORMATION structure contains information about one or more power supplies that are monitored by the power meter.
old-location: powermeter\pmi_metered_hardware_information.htm
old-project: powermeter
ms.assetid: 44dcfd41-7f0e-487e-8b08-5f301f17e7c1
ms.author: windowsdriverdev
ms.date: 11/6/2017
ms.keywords: _PMI_METERED_HARDWARE_INFORMATION, PMI_METERED_HARDWARE_INFORMATION, *PPMI_METERED_HARDWARE_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pmi.h
req.include-header: Pmi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PMI_METERED_HARDWARE_INFORMATION
req.alt-loc: pmi.h
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

# _PMI_METERED_HARDWARE_INFORMATION structure



## -description
The PMI_METERED_HARDWARE_INFORMATION structure contains information about one or more power supplies that are monitored by the power meter.


## -syntax

````
typedef struct _PMI_METERED_HARDWARE_INFORMATION {
  ULONG MeteredHardwareCount;
  WCHAR MeteredHardware[ANYSIZE_ARRAY];
} PMI_METERED_HARDWARE_INFORMATION, *PPMI_METERED_HARDWARE_INFORMATION;
````


## -struct-fields

### -field MeteredHardwareCount

A value that specifies the number of device identifiers that are returned in the <b>MeteredHardware</b> member.

### -field MeteredHardware

A Unicode string that specifies the name of each device that is powered by the circuit on which the power meter provides measurement data. Individual device paths are delimited by a <b>NULL</b> character, and the whole list is terminated with a double <b>NULL</b>. The format of the device name is \\Device\xyz". 
<div class="alert"><b>Note</b>  For systemwide power meters, this member returns <b>NULL</b>.</div>
<div> </div>

## -remarks
The PMI_METERED_HARDWARE_INFORMATION structure is returned through an <a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a> I/O control (IOCTL) query request. The input data for this query request is set to the <a href="..\pmi\ne-pmi-pmi_capabilities_type.md">PMI_CAPABILITIES_TYPE</a> enumerator value of <b>PmiMeteredHardware</b>.

If the query request completes successfully, the request returns a <a href="powermeter.pmi_capabilities">PMI_CAPABILITIES</a> structure. The <b>Capabilities</b> member of this structure is formatted as a PMI_METERED_HARDWARE_INFORMATION structure.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Pmi.h (include Pmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a>
</dt>
<dt>
<a href="powermeter.pmi_capabilities">PMI_CAPABILITIES</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20PMI_METERED_HARDWARE_INFORMATION structure%20 RELEASE:%20(11/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
