---
UID: NS:pmi._PMI_EVENT
title: _PMI_EVENT
author: windows-driver-content
description: The PMI_EVENT structure contains information about a power metering and budgeting event that is signaled through the Power Meter Interface (PMI).
old-location: powermeter\pmi_event.htm
old-project: powermeter
ms.assetid: 51ae6247-c482-4f13-8699-df871ae346c0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _PMI_EVENT, *PPMI_EVENT, PMI_EVENT
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
req.alt-api: PMI_EVENT
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
req.typenames: *PPMI_EVENT, PMI_EVENT
---

# _PMI_EVENT structure



## -description
The PMI_EVENT structure contains information about a power metering and budgeting event that is signaled through the Power Meter Interface (PMI).



## -syntax

````
typedef struct _PMI_EVENT {
  ULONG          Version;
  PMI_EVENT_TYPE EventType;
} PMI_EVENT, *PPMI_EVENT;
````


## -struct-fields

### -field Version

A value that specifies the version of this structure. For Windows 7, Windows Server 2008 R2, and later versions of Windows, this value must be 1.


### -field EventType

A <a href="..\pmi\ne-pmi-pmi_event_type.md">PMI_EVENT_TYPE</a> enumeration value that specifies the PMI event type.


## -remarks
The PMI_EVENT structure contains information about a power metering or budgeting event. PMI generates an event for a power meter when one of the following occurs:

The power meter's power metering or budgeting capabilities have changed.

The power meter's power metering or budgeting configurations have changed.

The power supply that is monitored by the power meter has exceeded the meter's configured power threshold.

The power supply that is monitored by the power meter has exceeded or fallen below the meter's configured power budget.

A user-mode service or application registers for notification of these events through an <a href="..\pmi\ni-pmi-ioctl_pmi_register_event_notify.md">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a> I/O control (IOCTL) query request. 

The PMI_EVENT structure does not contain the current PMI data for the event. Depending on the value of the <b>EventType</b> member, the caller can retrieve the current PMI data through a PMI IOCTL query request. The following table describes the PMI IOCTL to use to query the changed data from a power meter for a query request.

<b>PmiCapabilitiesChangedEvent</b>


<a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a>


The <b>AssociatedIrp.SystemBuffer</b> member is set to the address of an initiator-allocated buffer that contains any <a href="..\pmi\ne-pmi-pmi_capabilities_type.md">PMI_CAPABILITIES_TYPE</a> enumeration value.

<b>PmiConfigurationChangedEvent</b>


<a href="..\pmi\ni-pmi-ioctl_pmi_get_configuration.md">IOCTL_PMI_GET_CONFIGURATION</a>


The <b>AssociatedIrp.SystemBuffer</b> member is set to the address of an initiator-allocated buffer that contains any <a href="..\pmi\ne-pmi-pmi_configuration_type.md">PMI_CONFIGURATION_TYPE</a> enumeration value.

<b>PmiThresholdEvent</b>

The <b>AssociatedIrp.SystemBuffer</b> member is set to the address of an initiator-allocated buffer that contains the <a href="..\pmi\ne-pmi-pmi_configuration_type.md">PMI_CONFIGURATION_TYPE</a> enumeration value or <b>PmiThresholdConfiguration</b>.

<b>PmiBudgetEvent</b>

The <b>AssociatedIrp.SystemBuffer</b> member is set to the address of an initiator-allocated buffer that contains the <a href="..\pmi\ne-pmi-pmi_configuration_type.md">PMI_CONFIGURATION_TYPE</a> enumeration value or <b>PmiBudgetConfiguration</b>.

<b>PmiAveragingIntervalChangedEvent</b>

The <b>AssociatedIrp.SystemBuffer</b> member is set to the address of an initiator-allocated buffer that contains the <a href="..\pmi\ne-pmi-pmi_configuration_type.md">PMI_CONFIGURATION_TYPE</a> enumeration value or <b>PmiMeasurementConfiguration</b>.


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
<a href="..\pmi\ni-pmi-ioctl_pmi_get_configuration.md">IOCTL_PMI_GET_CONFIGURATION</a>
</dt>
<dt>
<a href="..\pmi\ni-pmi-ioctl_pmi_register_event_notify.md">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>
</dt>
<dt>
<a href="..\pmi\ne-pmi-pmi_event_type.md">PMI_EVENT_TYPE</a>
</dt>
<dt>
<a href="..\pmi\ne-pmi-pmi_capabilities_type.md">PMI_CAPABILITIES_TYPE</a>
</dt>
<dt>
<a href="..\pmi\ne-pmi-pmi_configuration_type.md">PMI_CONFIGURATION_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20PMI_EVENT structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

