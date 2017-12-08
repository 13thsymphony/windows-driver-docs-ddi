---
UID: NE.pmi.PMI_CAPABILITIES_TYPE
title: PMI_CAPABILITIES_TYPE
author: windows-driver-content
description: The PMI_CAPABILITIES_TYPE enumeration defines the type of capabilities data that is referenced by the Capability member of the PMI_CAPABILITIES structure.
old-location: powermeter\pmi_capabilities_type.htm
old-project: powermeter
ms.assetid: 6857f85b-c79a-4e80-a63f-1414aff61d1f
ms.author: windowsdriverdev
ms.date: 11/6/2017
ms.keywords: PMI_CAPABILITIES_TYPE, PMI_CAPABILITIES_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pmi.h
req.include-header: Pmi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PMI_CAPABILITIES_TYPE
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
req.irql: PASSIVE_LEVEL
---

# PMI_CAPABILITIES_TYPE enumeration



## -description
The PMI_CAPABILITIES_TYPE enumeration defines the type of capabilities data that is referenced by the <b>Capability</b> member of the <a href="powermeter.pmi_capabilities">PMI_CAPABILITIES</a> structure. This enumeration is also used to specify the type of <b>PMI_CAPABILITIES</b> structure to return through an <a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a> I/O control (IOCTL) request.


## -syntax

````
typedef enum  { 
  PmiReportedCapabilities,
  PmiMeteredHardware,
  PmiCapabilitiesMax
} PMI_CAPABILITIES_TYPE;
````


## -enum-fields

### -field PmiReportedCapabilities

The PMI capabilities data, formatted as a <a href="powermeter.pmi_reported_capabilities">PMI_REPORTED_CAPABILITIES</a> structure, specifies the power capabilities of the power meter.

### -field PmiMeteredHardware

The PMI capabilities data, formatted as a <a href="powermeter.pmi_metered_hardware_information">PMI_METERED_HARDWARE_INFORMATION</a> structure, specifies the hardware devices that the power meter provides measurement data to.

### -field PmiCapabilitiesMax

The maximum number of PMI capability structures.

## -remarks
The <b>CapabilityType</b> member of the <a href="powermeter.pmi_capabilities">PMI_CAPABILITIES</a> structure contains information about the type of PMI capability data that is referenced by the <b>Capabilities</b> member of that structure. This structure is returned through a successful completion of an <a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a> IOCTL request.

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
<dt>
<a href="powermeter.pmi_metered_hardware_information">PMI_METERED_HARDWARE_INFORMATION</a>
</dt>
<dt>
<a href="powermeter.pmi_reported_capabilities">PMI_REPORTED_CAPABILITIES</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20PMI_CAPABILITIES_TYPE enumeration%20 RELEASE:%20(11/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
