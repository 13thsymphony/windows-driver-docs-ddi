---
UID: NS.GNSSDRIVER.GNSS_BREADCRUMBING_PARAM
title: GNSS_BREADCRUMBING_PARAM
author: windows-driver-content
description: This structure contains the configuration passed into the start of breadcrumbing via IOCTL_GNSS_START_BREADCRUMBING.
old-location: sensors\gnss_breadcrumbing_param.htm
old-project: sensors
ms.assetid: 1EAD5B17-B662-4D97-B045-ED09E4AF6E99
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_BREADCRUMBING_PARAM, PGNSS_BREADCRUMBING_PARAM, GNSS_BREADCRUMBING_PARAM, *PGNSS_BREADCRUMBING_PARAM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GNSS_BREADCRUMBING_PARAM
req.alt-loc: gnssdriver.h
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

# GNSS_BREADCRUMBING_PARAM structure



## -description
This structure contains the configuration passed into the start of breadcrumbing via <a href="..\gnssdriver\ni-gnssdriver-ioctl_gnss_start_breadcrumbing.md">IOCTL_GNSS_START_BREADCRUMBING</a>.



## -syntax

````
typedef struct {
  ULONG Size;
  ULONG Version;
  ULONG MaximumHorizontalUncertainty;
  ULONG MinDistanceBetweenFixes;
  ULONG MaximumErrorTimeoutMs;
  BYTE  Unused[512];
} GNSS_BREADCRUMBING_PARAM, *PGNSS_BREADCRUMBING_PARAM;
````


## -struct-fields

### -field Size

Structure size.


### -field Version

Version number.


### -field MaximumHorizontalUncertainty

Contains the maximum horizontal uncertainty value. Any fix with an error radius larger than this value shall not be recorded.


### -field MinDistanceBetweenFixes

Contains the minimum distance between fixes. Only record a fix if the center of it is at least as  far apart as this value from center of the last fix, using a Haversine distance calculation.


### -field MaximumErrorTimeoutMs

Contains the maximum error timeout in milliseconds. If the location of the device is unknown for this duration, an error must be recorded in the breadcrumb data. Errors can be recorded earlier if they were already known.


### -field Unused[512]

Padding buffer.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Gnssdriver.h</dt>
</dl>
</td>
</tr>
</table>