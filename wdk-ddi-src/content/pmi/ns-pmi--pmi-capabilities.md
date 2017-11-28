---
UID: NS.pmi._PMI_CAPABILITIES
title: PMI_CAPABILITIES
author: windows-driver-content
description: The PMI_CAPABILITIES structure contains information about the power metering and budgeting capabilities of a power meter.
old-location: powermeter\pmi_capabilities.htm
old-project: powermeter
ms.assetid: 7e564512-ff57-4bce-93c1-76e6034ec061
ms.author: windowsdriverdev
ms.date: 11/6/2017
ms.keywords: PMI_CAPABILITIES, PMI_CAPABILITIES, *PPMI_CAPABILITIES
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
req.alt-api: PMI_CAPABILITIES
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
req.iface: 
---

# PMI_CAPABILITIES structure



## -description
<p>The PMI_CAPABILITIES structure contains information about the power metering and budgeting capabilities of a power meter.</p>


## -syntax

````
typedef struct _PMI_CAPABILITIES {
  ULONG                 Version;
  ULONG                 Size;
  PMI_CAPABILITIES_TYPE CapabilityType;
  union {
    PMI_REPORTED_CAPABILITIES        ReportedCapabilities;
    PMI_METERED_HARDWARE_INFORMATION MeteredHardwareInformation;
  } Capabilities;
} PMI_CAPABILITIES, *PPMI_CAPABILITIES;
````


## -struct-fields
<dl>

### -field <b>Version</b>

<dd>
<p>A value that specifies the version of this structure. For Windows 7, Windows Server 2008 R2, and later versions of Windows, this value must be 1.</p>
</dd>

### -field <b>Size</b>

<dd>
<p>A value, in units of bytes, that specifies the size of the structure.</p>
</dd>

### -field <b>CapabilityType</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff543864">PMI_CAPABILITIES_TYPE</a> enumeration value that specifies the data type of the <b>Capabilities</b> member.</p>
</dd>

### -field <b>Capabilities</b>

<dd>
<p>A union of the supported Power Meter Interface (PMI) capability structures. Based on the value of the <b>CapabilityType</b> member, one of the following <b>Capabilities</b> submembers is used to reference the following PMI capability structures:</p>
<dl>

### -field <b>ReportedCapabilities</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff543900">PMI_METERED_HARDWARE_INFORMATION</a> structure that specifies one or more hardware devices that are monitored by the power meter. </p>
<p>The <b>Capabilities</b> member contains this structure if the <b>CapabilityType</b> member is set to <b>PmiMeteredHardware</b>.</p>
</dd>

### -field <b>MeteredHardwareInformation</b>

<dd>
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff543902">PMI_REPORTED_CAPABILITIES</a> structure that specifies the PMI capabilities of the power meter, such as the following:</p>
<ul>
<li>Asset information 
</li>
<li>Measurement capabilities 
</li>
<li>Power and budget capabilities 
</li>
</ul>
<p>The <b>Capabilities</b> member contains this structure if the <b>CapabilityType</b> member is set to <b>PmiReportedCapabilities</b>.</p>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p>The PMI_CAPABILITIES structure is used to query many PMI capabilities that are supported by a power meter. </p>

<p>The PMI capability information is returned through an <a href="https://msdn.microsoft.com/library/windows/hardware/ff543837">IOCTL_PMI_GET_CAPABILITIES</a> I/O control (IOCTL) query request. The input data for this query request is set to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543864">PMI_CAPABILITIES_TYPE</a> enumerator value that specifies the type of PMI capability data to return.</p>

<p>If the IOCTL query request completes successfully, the request returns a PMI_CAPABILITIES structure. The <b>Capabilities</b> member of this structure contains data formatted as the requested PMI capabilities structure.</p>

<p>For example, if an IOCTL query request of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543837">IOCTL_PMI_GET_CAPABILITIES</a> is made with the input data set to <b>PmiReportedCapabilities</b> and the request completes successfully, the request returns a PMI_CAPABILITIES structure with its members set to the following values:</p>

<p>The <b>CapabilitiesType</b> member is set to <b>PmiReportedCapabilities</b>.</p>

<p>The <b>Capabilities</b> member contains data that is formatted as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543902">PMI_REPORTED_CAPABILITIES</a> structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543837">IOCTL_PMI_GET_CAPABILITIES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543864">PMI_CAPABILITIES_TYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543900">PMI_METERED_HARDWARE_INFORMATION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543902">PMI_REPORTED_CAPABILITIES</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20PMI_CAPABILITIES structure%20 RELEASE:%20(11/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
