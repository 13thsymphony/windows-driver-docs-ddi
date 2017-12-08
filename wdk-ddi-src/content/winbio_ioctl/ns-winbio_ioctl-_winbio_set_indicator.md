---
UID: NS.WINBIO_IOCTL._WINBIO_SET_INDICATOR
title: _WINBIO_SET_INDICATOR
author: windows-driver-content
description: The WINBIO_SET_INDICATOR structure is the IN payload for IOCTL_BIOMETRIC_SET_INDICATOR.
old-location: biometric\winbio_set_indicator.htm
old-project: biometric
ms.assetid: c4410845-3c7b-445e-80ec-25694b122a0e
ms.author: windowsdriverdev
ms.date: 11/13/2017
ms.keywords: _WINBIO_SET_INDICATOR, WINBIO_SET_INDICATOR, *PWINBIO_SET_INDICATOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winbio_ioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WINBIO_SET_INDICATOR
req.alt-loc: winbio_ioctl.h
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
req.product: Windows 10 or later.
---

# _WINBIO_SET_INDICATOR structure



## -description
The WINBIO_SET_INDICATOR structure is the IN payload for <a href="..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_set_indicator.md">IOCTL_BIOMETRIC_SET_INDICATOR</a>.


## -syntax

````
typedef struct _WINBIO_SET_INDICATOR {
  DWORD                   PayloadSize;
  WINBIO_INDICATOR_STATUS IndicatorStatus;
} WINBIO_SET_INDICATOR, *PWINBIO_SET_INDICATOR;
````


## -struct-fields

### -field PayloadSize

Specifies the total size of the payload, which includes the fixed length structure and any variable data at the end.

### -field IndicatorStatus

Specifies a WINBIO_INDICATOR_STATUS that indicates whether the indicator light should be set on or off.
 Possible values are shown in the following table. 
<table>
<tr>
<td>
Indicator status code
</td>
<td>
Description
</td>
</tr>
<tr>
<td>
WINBIO_INDICATOR_ON
</td>
<td>
The indicator light is on, and changes according to the sensor status.  To be able to set WINBIO_INDICATOR_ON, you must set WINBIO_CAPABILITY_INDICATOR in the <b>Capabilities</b> member of the WINBIO_SENSOR_ATTRIBUTES structure.
</td>
</tr>
<tr>
<td>
WINBIO_INDICATOR_OFF
</td>
<td>
The sensor indicator light is off.  Sensors that do not have an indicator light will always return this value in IOCTL_GET_SENSOR_STATUS. 
</td>
</tr>
</table>
 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows 7 and later versions of Windows.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Winbio_ioctl.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="biometric.winbio_get_indicator">WINBIO_GET_INDICATOR</a>
</dt>
<dt>
<a href="..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_set_indicator.md">IOCTL_BIOMETRIC_SET_INDICATOR</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [biometric\biometric]:%20WINBIO_SET_INDICATOR structure%20 RELEASE:%20(11/13/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
