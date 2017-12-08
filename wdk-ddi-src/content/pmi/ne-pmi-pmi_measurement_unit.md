---
UID: NE.pmi.PMI_MEASUREMENT_UNIT
title: PMI_MEASUREMENT_UNIT
author: windows-driver-content
description: The PMI_MEASUREMENT_UNIT enumeration defines the units of the PMI measurement data.
old-location: powermeter\pmi_measurement_unit.htm
old-project: powermeter
ms.assetid: 31f0239e-86d3-43e8-8627-7e16bd58df87
ms.author: windowsdriverdev
ms.date: 11/6/2017
ms.keywords: PMI_MEASUREMENT_UNIT, PMI_MEASUREMENT_UNIT
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
req.alt-api: PMI_MEASUREMENT_UNIT
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

# PMI_MEASUREMENT_UNIT enumeration



## -description
The PMI_MEASUREMENT_UNIT enumeration defines the units of the PMI measurement data.


## -syntax

````
typedef enum  { 
  PmiMeasurementUnitMilliWatt,
  PmiMeasurementUnitMax
} PMI_MEASUREMENT_UNIT;
````


## -enum-fields

### -field PmiMeasurementUnitMilliWatt

The PMI measurement data is in units of milliwatts (mW).

### -field PmiMeasurementUnitMax

The maximum types of PMI measurement units.

## -remarks
The <b>MeasurementUnit</b> member of the <a href="powermeter.pmi_reported_capabilities">PMI_REPORTED_CAPABILITIES</a> structure contains information about the measurement units of the data that is contained within the structure. This structure is returned through a successful completion of an <a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a> request.

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
<a href="powermeter.pmi_reported_capabilities">PMI_REPORTED_CAPABILITIES</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20PMI_MEASUREMENT_UNIT enumeration%20 RELEASE:%20(11/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
