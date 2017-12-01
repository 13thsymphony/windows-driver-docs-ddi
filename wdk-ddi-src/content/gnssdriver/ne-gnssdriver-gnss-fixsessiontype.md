---
UID: NE.gnssdriver.GNSS_FIXSESSIONTYPE
title: GNSS_FIXSESSIONTYPE
author: windows-driver-content
description: This enumeration indicates the type of location fix needed by the GNSS adapter when it issues an IOCTL_GNSS_START_FIXSESSION control code. This enumeration is set within the GNSS_FIXSESSION_PARAM structure.
old-location: sensors\gnss_fixsessiontype.htm
old-project: sensors
ms.assetid: CE611168-76B3-496F-91C7-932E1F259529
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_, FWPS_VSWITCH_EVENT_DISPATCH_TABLE0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GNSS_FIXSESSIONTYPE
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
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# GNSS_FIXSESSIONTYPE enumeration



## -description
<p>This enumeration indicates the type of location fix needed by the GNSS adapter when it issues an <a href="..\gnssdriver\ni-gnssdriver-ioctl-gnss-start-fixsession.md">IOCTL_GNSS_START_FIXSESSION</a> control code. This enumeration is set within the <a href="sensors.gnss_fixsession_param">GNSS_FIXSESSION_PARAM</a> structure.</p>


## -syntax

````
typedef enum  { 
  GNSS_FixSession_SingleShot          = 0x01,
  GNSS_FixSession_DistanceTracking    = 0x02,
  GNSS_FixSession_ContinuousTracking  = 0x03,
  GNSS_FixSession_LKG                 = 0x04
} GNSS_FIXSESSIONTYPE;
````


## -enum-fields
<dl>

### -field <a id="GNSS_FixSession_SingleShot"></a><a id="gnss_fixsession_singleshot"></a><a id="GNSS_FIXSESSION_SINGLESHOT"></a><b>GNSS_FixSession_SingleShot</b>

<dd>
<p>The session request is a single-shot request. The GNSS driver will return intermediate fixes on request. Once a final fix is delivered, no further fix will be returned for this fix session and the GNSS adapter issues a stop fix.</p>
</dd>

### -field <a id="GNSS_FixSession_DistanceTracking"></a><a id="gnss_fixsession_distancetracking"></a><a id="GNSS_FIXSESSION_DISTANCETRACKING"></a><b>GNSS_FixSession_DistanceTracking</b>

<dd>
<p>The start-fix request is for starting a tracking session such that a new fix is recorded and made available on request as soon as the device has moved beyond a specified threshold. No intermediate fix is required for a tracking session. A distance tracking session can be started even when another fix session of a different type is active. Both the fix sessions will continue getting the fixes as appropriate.</p>
</dd>

### -field <a id="GNSS_FixSession_ContinuousTracking"></a><a id="gnss_fixsession_continuoustracking"></a><a id="GNSS_FIXSESSION_CONTINUOUSTRACKING"></a><b>GNSS_FixSession_ContinuousTracking</b>

<dd>
<p>The start fix request is for starting a tracking session such that the device position is reported continuously.</p>
</dd>

### -field <a id="GNSS_FixSession_LKG"></a><a id="gnss_fixsession_lkg"></a><a id="GNSS_FIXSESSION_LKG"></a><b>GNSS_FixSession_LKG</b>

<dd>
<p>This session request is for a single-shot request, without starting any satellite acquisition/tracking activity by the underlying GNSS engine. The GNSS driver returns the cached copy (either from the engine or from the drivers own memory) of the last known position of the device, along with the timestamp. If no cached fix is available either in the engine or in the driver, an error is returned. No intermediate fix is returned for this session. Once the LKG fix or an error fix is returned the GNSS adapter issues a stop fix.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Gnssdriver.h</dt>
</dl>
</td>
</tr>
</table>