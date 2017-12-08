---
UID: NE.pmi.PMI_CONFIGURATION_TYPE
title: PMI_CONFIGURATION_TYPE
author: windows-driver-content
description: The PMI_CONFIGURATION_TYPE enumeration defines the type of PMI configuration data that is referenced by the Configuration member of the PMI_CONFIGURATION structure.
old-location: powermeter\pmi_configuration_type.htm
old-project: powermeter
ms.assetid: d5ffd580-ca3d-46c7-b0ba-1cd9962517f8
ms.author: windowsdriverdev
ms.date: 11/6/2017
ms.keywords: PMI_CONFIGURATION_TYPE, PMI_CONFIGURATION_TYPE
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
req.alt-api: PMI_CONFIGURATION_TYPE
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

# PMI_CONFIGURATION_TYPE enumeration



## -description
The PMI_CONFIGURATION_TYPE enumeration defines the type of PMI configuration data that is referenced by the <b>Configuration</b> member of the <a href="powermeter.pmi_configuration">PMI_CONFIGURATION</a> structure. This enumeration is also used to specify the type of <a href="powermeter.pmi_capabilities">PMI_CAPABILITIES</a> structure to return through an <a href="..\pmi\ni-pmi-ioctl_pmi_get_configuration.md">IOCTL_PMI_GET_CONFIGURATION</a> I/O control (IOCTL) request.


## -syntax

````
typedef enum  { 
  PmiMeasurementConfiguration,
  PmiBudgetingConfiguration,
  PmiThresholdConfiguration,
  PmiConfigurationMax
} PMI_CONFIGURATION_TYPE;
````


## -enum-fields

### -field PmiMeasurementConfiguration

The PMI configuration data, formatted as a <a href="powermeter.pmi_measurement_configuration">PMI_MEASUREMENT_CONFIGURATION</a> structure, contains information about the measurement configuration of the power meter.

### -field PmiBudgetingConfiguration

The PMI configuration data, formatted as a <a href="powermeter.pmi_budgeting_configuration">PMI_BUDGETING_CONFIGURATION</a> structure, contains information about the budgeting configuration of the power meter.

### -field PmiThresholdConfiguration

The PMI configuration data, formatted as a <a href="powermeter.pmi_threshold_configuration">PMI_THRESHOLD_CONFIGURATION</a> structure, contains information about the budgeting configuration of the power meter.

### -field PmiConfigurationMax

The maximum number of PMI configuration structures.

## -remarks
The <b>ConfigurationType</b> member of the <a href="powermeter.pmi_configuration">PMI_CONFIGURATION</a> structure contains information about the type of PMI configuration data that is referenced by the <b>Configuration</b> member of that structure. This structure is returned through a successful completion of an <a href="..\pmi\ni-pmi-ioctl_pmi_get_configuration.md">IOCTL_PMI_GET_CONFIGURATION</a> IOCTL request and is passed in the input buffer for an <a href="..\pmi\ni-pmi-ioctl_pmi_set_configuration.md">IOCTL_PMI_SET_CONFIGURATION</a> IOCTL request.

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
<a href="..\pmi\ni-pmi-ioctl_pmi_get_configuration.md">IOCTL_PMI_GET_CONFIGURATION</a>
</dt>
<dt>
<a href="..\pmi\ni-pmi-ioctl_pmi_set_configuration.md">IOCTL_PMI_SET_CONFIGURATION</a>
</dt>
<dt>
<a href="powermeter.pmi_budgeting_configuration">PMI_BUDGETING_CONFIGURATION</a>
</dt>
<dt>
<a href="powermeter.pmi_configuration">PMI_CONFIGURATION</a>
</dt>
<dt>
<a href="powermeter.pmi_measurement_configuration">PMI_MEASUREMENT_CONFIGURATION</a>
</dt>
<dt>
<a href="powermeter.pmi_threshold_configuration">PMI_THRESHOLD_CONFIGURATION</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20PMI_CONFIGURATION_TYPE enumeration%20 RELEASE:%20(11/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
