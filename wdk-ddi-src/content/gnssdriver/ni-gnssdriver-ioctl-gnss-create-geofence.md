---
UID: NI.gnssdriver.IOCTL_GNSS_CREATE_GEOFENCE
title: IOCTL_GNSS_CREATE_GEOFENCE
author: windows-driver-content
description: The IOCTL_GNSS_CREATE_GEOFENCE control code is used by the GNSS adapter to create a geofence.
old-location: sensors\ioctl_gnss_create_geofence.htm
old-project: sensors
ms.assetid: 114B7E39-1FC6-4AC4-A238-3FC3D4A122B0
ms.author: windowsdriverdev
ms.date: 11/26/2017
ms.keywords: FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_, FWPS_VSWITCH_EVENT_DISPATCH_TABLE0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_GNSS_CREATE_GEOFENCE
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
req.iface: 
---

# IOCTL_GNSS_CREATE_GEOFENCE IOCTL



## -description
<p>The <b>IOCTL_GNSS_CREATE_GEOFENCE</b> 
   control code is used by the GNSS adapter to create a geofence.
</p>


## -ioctlparameters

### -input-buffer
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn925162">GNSS_GEOFENCE_CREATE_PARAM</a> structure that defines the geofence to be created.

</p>

### -input-buffer-length
<p>Set to sizeof(<b>GNSS_GEOFENCE_CREATE_PARAM</b>).

</p>

<p>Set to sizeof(<b>GNSS_GEOFENCE_CREATE_PARAM</b>).

</p>

### -output-buffer
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn925165">GNSS_GEOFENCE_CREATE_RESPONSE</a> structure.</p>

<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn925165">GNSS_GEOFENCE_CREATE_RESPONSE</a> structure.</p>

<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn925165">GNSS_GEOFENCE_CREATE_RESPONSE</a> structure.</p>

### -output-buffer-length
<p>Set to sizeof(<b>GNSS_GEOFENCE_CREATE_RESPONSE</b>).</p>

<p>Set to sizeof(<b>GNSS_GEOFENCE_CREATE_RESPONSE</b>).</p>

<p>Set to sizeof(<b>GNSS_GEOFENCE_CREATE_RESPONSE</b>).</p>

<p>Set to sizeof(<b>GNSS_GEOFENCE_CREATE_RESPONSE</b>).</p>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

## -remarks
<p>If the call is successful, the GNSS engine registers the geofence and assigns a unique ID. The GNSS adapter uses the unique ID for all interaction with the driver regarding this specific geofence.
</p>

<p>If the call fails, the GNSS driver must ensure that the GNSS engine does not end up creating the geofence and start tracking it. A failure should roll the state of the GNSS engine back to the previous state before adding this geofence.
</p>

<p>The GNSS adapter does not expect the driver to persist the geofences across driver restarts. The GNSS adapter explicitly clears all geofences from the GNSS driver through the <b>GNSS_ResetGeofencesTracking</b> command at appropriate times (initialization, tracking status change after a failure, etc.).</p>

<p>If this is the first geofence, the GNSS driver should start geofence tracking, continue monitoring the geofence against the current location of the device in a power efficient manner, and raise alerts if a geofence is breached. If the GNSS engine is unable to track the geofence (due to bad signal conditions or other transient errors), an error status must be raised through the <b>LISTEN_GEOFENCES_TRACKINGSTATUS</b> event.</p>

<p>The GNSS engine must adhere to the following guidelines for geofence tracking:</p>

<p>The device tracking operation and breach detection must be optimized to take into account the size and area of the geofence. If all conditions are  the same, larger geofences should be tracked less aggressively compared to smaller geofences.</p>

<p>The device tracking operation must be dynamically optimized to take into account the relative distance of the geofence with respect to the current position. All conditions being equal, farther geofences should be tracked less aggressively compared to the closer ones and the aggression should increase as the device gets closer to the geofence.</p>

<p>The breach detection mechanism must be asymmetric for entry and exit. As a general rule, the rules for determining exit from a geofence should be relaxed compared to the rules for determining entry into the geofence.</p>

<p>The breach detection mechanism must take into account potential false positives arising due to the inherent inaccuracy of device location. For example, if the device is hovering near the edge of a geofence, a sub-optimal breach detection mechanism may generate too many entry and exit events back to back even if the device is not physically moving in and out. Asymmetric exit detection and hysteresis are typical measures to avoid such errors.</p>

<p>The device tracking operation of the GNSS engine must use all forms of available location changed signals that are either available on the SoC or can be used at low-power. Such signals may include, but not limited to, data from accelerometer and other sensors, cellular signal change, WiFi connect/disconnect, and so on.</p>

<p>The geofence tracking and breach detection operations must be entirely implemented in the GNSS engine on SoC. Neither the GNSS driver nor any other extension component on the application processor should wake up for device tracking or breach detection.</p>

<p>The GNSS driver and the GNSS engine must expose documented IHV-specific tuning parameters to facilitate performance and power tuning of the geofence tracking functionality. Microsoft and OEMs will make use of  tuning parameters and determine the right balance between the quality of service, reliability, and power cost of the geofence experience end-to-end. Tuning parameters can be made available either through registry settings or through IHV SoC configuration data.</p>

<p>If the call is successful, the GNSS engine registers the geofence and assigns a unique ID. The GNSS adapter uses the unique ID for all interaction with the driver regarding this specific geofence.
</p>

<p>If the call fails, the GNSS driver must ensure that the GNSS engine does not end up creating the geofence and start tracking it. A failure should roll the state of the GNSS engine back to the previous state before adding this geofence.
</p>

<p>The GNSS adapter does not expect the driver to persist the geofences across driver restarts. The GNSS adapter explicitly clears all geofences from the GNSS driver through the <b>GNSS_ResetGeofencesTracking</b> command at appropriate times (initialization, tracking status change after a failure, etc.).</p>

<p>If this is the first geofence, the GNSS driver should start geofence tracking, continue monitoring the geofence against the current location of the device in a power efficient manner, and raise alerts if a geofence is breached. If the GNSS engine is unable to track the geofence (due to bad signal conditions or other transient errors), an error status must be raised through the <b>LISTEN_GEOFENCES_TRACKINGSTATUS</b> event.</p>

<p>The GNSS engine must adhere to the following guidelines for geofence tracking:</p>

<p>The device tracking operation and breach detection must be optimized to take into account the size and area of the geofence. If all conditions are  the same, larger geofences should be tracked less aggressively compared to smaller geofences.</p>

<p>The device tracking operation must be dynamically optimized to take into account the relative distance of the geofence with respect to the current position. All conditions being equal, farther geofences should be tracked less aggressively compared to the closer ones and the aggression should increase as the device gets closer to the geofence.</p>

<p>The breach detection mechanism must be asymmetric for entry and exit. As a general rule, the rules for determining exit from a geofence should be relaxed compared to the rules for determining entry into the geofence.</p>

<p>The breach detection mechanism must take into account potential false positives arising due to the inherent inaccuracy of device location. For example, if the device is hovering near the edge of a geofence, a sub-optimal breach detection mechanism may generate too many entry and exit events back to back even if the device is not physically moving in and out. Asymmetric exit detection and hysteresis are typical measures to avoid such errors.</p>

<p>The device tracking operation of the GNSS engine must use all forms of available location changed signals that are either available on the SoC or can be used at low-power. Such signals may include, but not limited to, data from accelerometer and other sensors, cellular signal change, WiFi connect/disconnect, and so on.</p>

<p>The geofence tracking and breach detection operations must be entirely implemented in the GNSS engine on SoC. Neither the GNSS driver nor any other extension component on the application processor should wake up for device tracking or breach detection.</p>

<p>The GNSS driver and the GNSS engine must expose documented IHV-specific tuning parameters to facilitate performance and power tuning of the geofence tracking functionality. Microsoft and OEMs will make use of  tuning parameters and determine the right balance between the quality of service, reliability, and power cost of the geofence experience end-to-end. Tuning parameters can be made available either through registry settings or through IHV SoC configuration data.</p>

<p>If the call is successful, the GNSS engine registers the geofence and assigns a unique ID. The GNSS adapter uses the unique ID for all interaction with the driver regarding this specific geofence.
</p>

<p>If the call fails, the GNSS driver must ensure that the GNSS engine does not end up creating the geofence and start tracking it. A failure should roll the state of the GNSS engine back to the previous state before adding this geofence.
</p>

<p>The GNSS adapter does not expect the driver to persist the geofences across driver restarts. The GNSS adapter explicitly clears all geofences from the GNSS driver through the <b>GNSS_ResetGeofencesTracking</b> command at appropriate times (initialization, tracking status change after a failure, etc.).</p>

<p>If this is the first geofence, the GNSS driver should start geofence tracking, continue monitoring the geofence against the current location of the device in a power efficient manner, and raise alerts if a geofence is breached. If the GNSS engine is unable to track the geofence (due to bad signal conditions or other transient errors), an error status must be raised through the <b>LISTEN_GEOFENCES_TRACKINGSTATUS</b> event.</p>

<p>The GNSS engine must adhere to the following guidelines for geofence tracking:</p>

<p>The device tracking operation and breach detection must be optimized to take into account the size and area of the geofence. If all conditions are  the same, larger geofences should be tracked less aggressively compared to smaller geofences.</p>

<p>The device tracking operation must be dynamically optimized to take into account the relative distance of the geofence with respect to the current position. All conditions being equal, farther geofences should be tracked less aggressively compared to the closer ones and the aggression should increase as the device gets closer to the geofence.</p>

<p>The breach detection mechanism must be asymmetric for entry and exit. As a general rule, the rules for determining exit from a geofence should be relaxed compared to the rules for determining entry into the geofence.</p>

<p>The breach detection mechanism must take into account potential false positives arising due to the inherent inaccuracy of device location. For example, if the device is hovering near the edge of a geofence, a sub-optimal breach detection mechanism may generate too many entry and exit events back to back even if the device is not physically moving in and out. Asymmetric exit detection and hysteresis are typical measures to avoid such errors.</p>

<p>The device tracking operation of the GNSS engine must use all forms of available location changed signals that are either available on the SoC or can be used at low-power. Such signals may include, but not limited to, data from accelerometer and other sensors, cellular signal change, WiFi connect/disconnect, and so on.</p>

<p>The geofence tracking and breach detection operations must be entirely implemented in the GNSS engine on SoC. Neither the GNSS driver nor any other extension component on the application processor should wake up for device tracking or breach detection.</p>

<p>The GNSS driver and the GNSS engine must expose documented IHV-specific tuning parameters to facilitate performance and power tuning of the geofence tracking functionality. Microsoft and OEMs will make use of  tuning parameters and determine the right balance between the quality of service, reliability, and power cost of the geofence experience end-to-end. Tuning parameters can be made available either through registry settings or through IHV SoC configuration data.</p>

<p>If the call is successful, the GNSS engine registers the geofence and assigns a unique ID. The GNSS adapter uses the unique ID for all interaction with the driver regarding this specific geofence.
</p>

<p>If the call fails, the GNSS driver must ensure that the GNSS engine does not end up creating the geofence and start tracking it. A failure should roll the state of the GNSS engine back to the previous state before adding this geofence.
</p>

<p>The GNSS adapter does not expect the driver to persist the geofences across driver restarts. The GNSS adapter explicitly clears all geofences from the GNSS driver through the <b>GNSS_ResetGeofencesTracking</b> command at appropriate times (initialization, tracking status change after a failure, etc.).</p>

<p>If this is the first geofence, the GNSS driver should start geofence tracking, continue monitoring the geofence against the current location of the device in a power efficient manner, and raise alerts if a geofence is breached. If the GNSS engine is unable to track the geofence (due to bad signal conditions or other transient errors), an error status must be raised through the <b>LISTEN_GEOFENCES_TRACKINGSTATUS</b> event.</p>

<p>The GNSS engine must adhere to the following guidelines for geofence tracking:</p>

<p>The device tracking operation and breach detection must be optimized to take into account the size and area of the geofence. If all conditions are  the same, larger geofences should be tracked less aggressively compared to smaller geofences.</p>

<p>The device tracking operation must be dynamically optimized to take into account the relative distance of the geofence with respect to the current position. All conditions being equal, farther geofences should be tracked less aggressively compared to the closer ones and the aggression should increase as the device gets closer to the geofence.</p>

<p>The breach detection mechanism must be asymmetric for entry and exit. As a general rule, the rules for determining exit from a geofence should be relaxed compared to the rules for determining entry into the geofence.</p>

<p>The breach detection mechanism must take into account potential false positives arising due to the inherent inaccuracy of device location. For example, if the device is hovering near the edge of a geofence, a sub-optimal breach detection mechanism may generate too many entry and exit events back to back even if the device is not physically moving in and out. Asymmetric exit detection and hysteresis are typical measures to avoid such errors.</p>

<p>The device tracking operation of the GNSS engine must use all forms of available location changed signals that are either available on the SoC or can be used at low-power. Such signals may include, but not limited to, data from accelerometer and other sensors, cellular signal change, WiFi connect/disconnect, and so on.</p>

<p>The geofence tracking and breach detection operations must be entirely implemented in the GNSS engine on SoC. Neither the GNSS driver nor any other extension component on the application processor should wake up for device tracking or breach detection.</p>

<p>The GNSS driver and the GNSS engine must expose documented IHV-specific tuning parameters to facilitate performance and power tuning of the geofence tracking functionality. Microsoft and OEMs will make use of  tuning parameters and determine the right balance between the quality of service, reliability, and power cost of the geofence experience end-to-end. Tuning parameters can be made available either through registry settings or through IHV SoC configuration data.</p>

<p>If the call is successful, the GNSS engine registers the geofence and assigns a unique ID. The GNSS adapter uses the unique ID for all interaction with the driver regarding this specific geofence.
</p>

<p>If the call fails, the GNSS driver must ensure that the GNSS engine does not end up creating the geofence and start tracking it. A failure should roll the state of the GNSS engine back to the previous state before adding this geofence.
</p>

<p>The GNSS adapter does not expect the driver to persist the geofences across driver restarts. The GNSS adapter explicitly clears all geofences from the GNSS driver through the <b>GNSS_ResetGeofencesTracking</b> command at appropriate times (initialization, tracking status change after a failure, etc.).</p>

<p>If this is the first geofence, the GNSS driver should start geofence tracking, continue monitoring the geofence against the current location of the device in a power efficient manner, and raise alerts if a geofence is breached. If the GNSS engine is unable to track the geofence (due to bad signal conditions or other transient errors), an error status must be raised through the <b>LISTEN_GEOFENCES_TRACKINGSTATUS</b> event.</p>

<p>The GNSS engine must adhere to the following guidelines for geofence tracking:</p>

<p>The device tracking operation and breach detection must be optimized to take into account the size and area of the geofence. If all conditions are  the same, larger geofences should be tracked less aggressively compared to smaller geofences.</p>

<p>The device tracking operation must be dynamically optimized to take into account the relative distance of the geofence with respect to the current position. All conditions being equal, farther geofences should be tracked less aggressively compared to the closer ones and the aggression should increase as the device gets closer to the geofence.</p>

<p>The breach detection mechanism must be asymmetric for entry and exit. As a general rule, the rules for determining exit from a geofence should be relaxed compared to the rules for determining entry into the geofence.</p>

<p>The breach detection mechanism must take into account potential false positives arising due to the inherent inaccuracy of device location. For example, if the device is hovering near the edge of a geofence, a sub-optimal breach detection mechanism may generate too many entry and exit events back to back even if the device is not physically moving in and out. Asymmetric exit detection and hysteresis are typical measures to avoid such errors.</p>

<p>The device tracking operation of the GNSS engine must use all forms of available location changed signals that are either available on the SoC or can be used at low-power. Such signals may include, but not limited to, data from accelerometer and other sensors, cellular signal change, WiFi connect/disconnect, and so on.</p>

<p>The geofence tracking and breach detection operations must be entirely implemented in the GNSS engine on SoC. Neither the GNSS driver nor any other extension component on the application processor should wake up for device tracking or breach detection.</p>

<p>The GNSS driver and the GNSS engine must expose documented IHV-specific tuning parameters to facilitate performance and power tuning of the geofence tracking functionality. Microsoft and OEMs will make use of  tuning parameters and determine the right balance between the quality of service, reliability, and power cost of the geofence experience end-to-end. Tuning parameters can be made available either through registry settings or through IHV SoC configuration data.</p>

<p>If the call is successful, the GNSS engine registers the geofence and assigns a unique ID. The GNSS adapter uses the unique ID for all interaction with the driver regarding this specific geofence.
</p>

<p>If the call fails, the GNSS driver must ensure that the GNSS engine does not end up creating the geofence and start tracking it. A failure should roll the state of the GNSS engine back to the previous state before adding this geofence.
</p>

<p>The GNSS adapter does not expect the driver to persist the geofences across driver restarts. The GNSS adapter explicitly clears all geofences from the GNSS driver through the <b>GNSS_ResetGeofencesTracking</b> command at appropriate times (initialization, tracking status change after a failure, etc.).</p>

<p>If this is the first geofence, the GNSS driver should start geofence tracking, continue monitoring the geofence against the current location of the device in a power efficient manner, and raise alerts if a geofence is breached. If the GNSS engine is unable to track the geofence (due to bad signal conditions or other transient errors), an error status must be raised through the <b>LISTEN_GEOFENCES_TRACKINGSTATUS</b> event.</p>

<p>The GNSS engine must adhere to the following guidelines for geofence tracking:</p>

<p>The device tracking operation and breach detection must be optimized to take into account the size and area of the geofence. If all conditions are  the same, larger geofences should be tracked less aggressively compared to smaller geofences.</p>

<p>The device tracking operation must be dynamically optimized to take into account the relative distance of the geofence with respect to the current position. All conditions being equal, farther geofences should be tracked less aggressively compared to the closer ones and the aggression should increase as the device gets closer to the geofence.</p>

<p>The breach detection mechanism must be asymmetric for entry and exit. As a general rule, the rules for determining exit from a geofence should be relaxed compared to the rules for determining entry into the geofence.</p>

<p>The breach detection mechanism must take into account potential false positives arising due to the inherent inaccuracy of device location. For example, if the device is hovering near the edge of a geofence, a sub-optimal breach detection mechanism may generate too many entry and exit events back to back even if the device is not physically moving in and out. Asymmetric exit detection and hysteresis are typical measures to avoid such errors.</p>

<p>The device tracking operation of the GNSS engine must use all forms of available location changed signals that are either available on the SoC or can be used at low-power. Such signals may include, but not limited to, data from accelerometer and other sensors, cellular signal change, WiFi connect/disconnect, and so on.</p>

<p>The geofence tracking and breach detection operations must be entirely implemented in the GNSS engine on SoC. Neither the GNSS driver nor any other extension component on the application processor should wake up for device tracking or breach detection.</p>

<p>The GNSS driver and the GNSS engine must expose documented IHV-specific tuning parameters to facilitate performance and power tuning of the geofence tracking functionality. Microsoft and OEMs will make use of  tuning parameters and determine the right balance between the quality of service, reliability, and power cost of the geofence experience end-to-end. Tuning parameters can be made available either through registry settings or through IHV SoC configuration data.</p>

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

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_CREATE_GEOFENCE control code%20 RELEASE:%20(11/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
