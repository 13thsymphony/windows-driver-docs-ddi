---
UID: NS.ksmedia.tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
title: tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
author: windows-driver-content
description: The KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING is a property payload structure for video processing settings related to white balance, exposure mode, and focus mode.
old-location: stream\kscamera_extendedprop_videoprocsetting.htm
ms.assetid: D4239E72-C57A-45BC-881C-08FF6263874E
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: stream
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
req.alt-loc: Ksmedia.h
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
ms.keywords: tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, *PKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING
req.iface: 
---

# tagKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING structure



## -description
<p>The <b>KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING</b> is a property payload structure for video processing settings related to white balance, exposure mode, and focus mode.</p>


## -syntax

````
typedef struct _KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING {
  ULONG                       Mode;
  LONG                        Min;
  LONG                        Max;
  LONG                        Step;
  KSCAMERA_EXTENDEDPROP_VALUE VideoProc;
  ULONGLONG                   Reserved;
} KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING, *PKSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING;
````


## -struct-fields
<dl>

### -field <b>Mode</b>

<dd>
<p>The video processing mode type. Currently, this member is used to control white balance. The possible values for <b>Mode</b> are the following.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_WHITEBALANCE_TEMPERATURE"></a><a id="kscamera_extendedprop_whitebalance_temperature"></a><dl>

### -field <b>KSCAMERA_EXTENDEDPROP_WHITEBALANCE_TEMPERATURE</b>

</dl>
</td>
<td width="60%">
<p>A picture temperature value is used to set white balance in degrees Kelvin.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_WHITEBALANCE_PRESET"></a><a id="kscamera_extendedprop_whitebalance_preset"></a><dl>

### -field <b>KSCAMERA_EXTENDEDPROP_WHITEBALANCE_PRESET</b>

</dl>
</td>
<td width="60%">
<p>The white balance setting is a preset value specified in <b>VideoProc</b>.</p>
</td>
</tr>
</table>
<p> </p>
<p>This member is not used for <a href="https://msdn.microsoft.com/library/windows/hardware/dn567573">KSPROPERTY_CAMERACONTROL_EXTENDED_EXPOSUREMODE</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/dn567576">KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSMODE</a>. In these cases it must be set to 0.</p>
</dd>

### -field <b>Min</b>

<dd>
<p>The minum range value for the setting in <b>VideoProc</b>.</p>
</dd>

### -field <b>Max</b>

<dd>
<p>The maximum range value for the setting in <b>VideoProc</b>.</p>
</dd>

### -field <b>Step</b>

<dd>
<p>The maximum range value for the setting in <b>VideoProc</b>.</p>
<p>The increment in value, when applicable, for the setting in <b>VideoProc</b> when <b>Mode</b> is set to KSCAMERA_EXTENDEDPROP_WHITEBALANCE_TEMPERATURE.</p>
<p>-or-</p>
<p>The increment in value, when applicable, for the setting in <b>VideoProc</b> when setting exposure is set manually with KSCAMERA_EXTENDEDPROP_VIDEOPROCFLAG_MANUAL.</p>
</dd>

### -field <b>VideoProc</b>

<dd>
<p>Using the <a href="https://msdn.microsoft.com/library/windows/hardware/dn567588">KSPROPERTY_CAMERACONTROL_EXTENDED_WHITEBALANCEMODE</a> property, when <b>Mode</b> is set to KSCAMERA_EXTENDEDPROP_WHITEBALANCE_PRESET, the <b>VideoProc.Value.ul</b> value is one of the following.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_WBPRESET_CLOUDY"></a><a id="kscamera_extendedprop_wbpreset_cloudy"></a><dl>

### -field <b>KSCAMERA_EXTENDEDPROP_WBPRESET_CLOUDY</b>

</dl>
</td>
<td width="60%">
<p>White balance preset for cloudy conditions.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_WBPRESET_DAYLIGHT"></a><a id="kscamera_extendedprop_wbpreset_daylight"></a><dl>

### -field <b>KSCAMERA_EXTENDEDPROP_WBPRESET_DAYLIGHT</b>

</dl>
</td>
<td width="60%">
<p>White balance preset for cloudy daylight.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_WBPRESET_FLASH"></a><a id="kscamera_extendedprop_wbpreset_flash"></a><dl>

### -field <b>KSCAMERA_EXTENDEDPROP_WBPRESET_FLASH</b>

</dl>
</td>
<td width="60%">
<p>White balance preset to compensate for flash lighting.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_WBPRESET_FLUORESCENT"></a><a id="kscamera_extendedprop_wbpreset_fluorescent"></a><dl>

### -field <b>KSCAMERA_EXTENDEDPROP_WBPRESET_FLUORESCENT</b>

</dl>
</td>
<td width="60%">
<p>White balance preset to compensate for fluorescent lighting.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_WBPRESET_TUNGSTEN"></a><a id="kscamera_extendedprop_wbpreset_tungsten"></a><dl>

### -field <b>KSCAMERA_EXTENDEDPROP_WBPRESET_TUNGSTEN</b>

</dl>
</td>
<td width="60%">
<p>White balance preset to compensate for tungsten emitted lighting.</p>
</td>
</tr>
<tr>
<td width="40%"><a id="KSCAMERA_EXTENDEDPROP_WBPRESET_CANDLELIGHT"></a><a id="kscamera_extendedprop_wbpreset_candlelight"></a><dl>

### -field <b>KSCAMERA_EXTENDEDPROP_WBPRESET_CANDLELIGHT</b>

</dl>
</td>
<td width="60%">
<p>White balance preset to compensate for candlelight lighting.</p>
</td>
</tr>
</table>
<p> </p>
<p>Using the <a href="https://msdn.microsoft.com/library/windows/hardware/dn567588">KSPROPERTY_CAMERACONTROL_EXTENDED_WHITEBALANCEMODE</a> property, when <b>Mode</b> is set to KSCAMERA_EXTENDEDPROP_WHITEBALANCE_TEMPERATURE, the <b>VideoProc.Value.ul</b> value is a temperature value in degrees Kelvin.</p>
<p>Using the  <a href="https://msdn.microsoft.com/library/windows/hardware/dn567573">KSPROPERTY_CAMERACONTROL_EXTENDED_EXPOSUREMODE</a> property, when used for manually setting exposure, KSCAMERA_EXTENDEDPROP_VIDEOPROCFLAG_MANUAL, the <b>VideoProc.Value.ul</b> value is a the exposure time in 100 nanosecond units.</p>
<p>Using the <a href="https://msdn.microsoft.com/library/windows/hardware/dn567576">KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSMODE</a> property, this member contains the focal length value for manual focus mode,  KSCAMERA_EXTENDEDPROP_VIDEOPROCFLAG_MANUAL.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Reserved.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 8.1.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ksmedia.h (include Ksmedia.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn567573">KSPROPERTY_CAMERACONTROL_EXTENDED_EXPOSUREMODE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn567576">KSPROPERTY_CAMERACONTROL_EXTENDED_FOCUSMODE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn567588">KSPROPERTY_CAMERACONTROL_EXTENDED_WHITEBALANCEMODE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSCAMERA_EXTENDEDPROP_VIDEOPROCSETTING structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
