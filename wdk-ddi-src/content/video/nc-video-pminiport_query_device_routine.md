---
UID: NC.video.PMINIPORT_QUERY_DEVICE_ROUTINE
title: PMINIPORT_QUERY_DEVICE_ROUTINE
author: windows-driver-content
description: HwVidQueryDeviceCallback uses the specified configuration data to configure its adapter, and, possibly, to fill in missing configuration information in the VIDEO_PORT_CONFIG_INFO structure.
old-location: display\hwvidquerydevicecallback.htm
old-project: display
ms.assetid: 81c3f484-427e-43b8-b7dd-12017533560b
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _VHF_CONFIG, VHF_CONFIG, *PVHF_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HwVidQueryDeviceCallback
req.alt-loc: video.h
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

# PMINIPORT_QUERY_DEVICE_ROUTINE callback



## -description
<i>HwVidQueryDeviceCallback</i> uses the specified configuration data to configure its adapter, and, possibly, to fill in missing configuration information in the <a href="display.video_port_config_info">VIDEO_PORT_CONFIG_INFO</a> structure.


## -prototype

````
PMINIPORT_QUERY_DEVICE_ROUTINE HwVidQueryDeviceCallback;

VP_STATUS HwVidQueryDeviceCallback(
   PVOID                  HwDeviceExtension,
   PVOID                  Context,
   VIDEO_DEVICE_DATA_TYPE DeviceDataType,
   PVOID                  Identifier,
   ULONG                  IdentifierLength,
   PVOID                  ConfigurationData,
   ULONG                  ConfigurationDataLength,
   PVOID                  ComponentInformation,
   ULONG                  ComponentInformationLength
)
{ ... }
````


## -parameters

### -param HwDeviceExtension 

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.

### -param Context 

Pointer to the context value set up by <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a>. Usually, it points to the VIDEO_PORT_CONFIG_INFO buffer or to an offset in that buffer.

### -param DeviceDataType 

Specifies the type of configuration information that was requested, which is one of the following:
<dl>
<dd>
<b>VpBusData</b>
</dd>
<dd>
<b><b>VpCmosData</b></b>
</dd>
<dd>
<b><b>VpControllerData</b></b>
</dd>
<dd>
<b><b>VpMachineData</b></b>
</dd>
<dd>
<b><b>VpMonitorData</b></b>
</dd>
</dl>
Miniport drivers of x86-type video adapters usually specify <b>VpBusData</b>, particularly for adapters on EISA buses. The <b>VpControllerData</b> and <b>VpMonitorData</b> values have meaning only on ARC-compliant platforms. The <b>VpCmosData</b> and <b>VpMachineData</b> values are seldom used.  

### -param Identifier 

Pointer to the name of the device as determined by the ARC firmware. This parameter should be used only on ARC-compliant platforms. Otherwise, this pointer should be <b>NULL</b>.

### -param IdentifierLength 

Specifies the size in bytes of the buffered <i>Identifier</i> string<i>.</i> The value should be zero if the machine is not ARC-compliant.

### -param ConfigurationData 

Pointer to hardware configuration data. The format of this data is determined by the specified <i>DeviceDataType</i> and by the <b>AdapterInterfaceType</b> value in the VIDEO_PORT_CONFIG_INFO.

### -param ConfigurationDataLength 

Specifies the size in bytes of the <i>ConfigurationData</i> buffer. In effect, this indicates how much information was collected from the registry and stored in the <i>ConfigurationData</i> buffer allocated by <a href="display.videoportgetdevicebase">VideoPortGetDeviceBase</a>.

### -param ComponentInformation 

Reserved for system use.

### -param ComponentInformationLength 

Reserved for system use.

## -returns
<i>HwVidQueryDeviceCallback</i> returns the status of the operation.

## -remarks
<i>HwVidQueryDeviceCallback</i> is passed in a call to <a href="display.videoportgetdevicedata">VideoPortGetDeviceData</a> from the miniport driver's <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a> function. <b>VideoPortGetDeviceData</b> calls <i>HwVidQueryDeviceCallback</i> after collecting available configuration information under the <b>\Registry\Machine\Hardware\Description</b> node of the registry.

<i>HwVidQueryDeviceCallback</i> examines the <i>ConfigurationData</i>, collected from the registry by <b>VideoPortGetDeviceData</b>. It uses this information to configure its adapter, and, possibly, to fill in missing configuration information in the <a href="display.video_port_config_info">VIDEO_PORT_CONFIG_INFO</a> structure.

<i>HwVidQueryDeviceCallback</i> cannot pass access range values found in the <i>ConfigurationData</i> to any <b>VideoPortRead</b><i>Xxx</i> or <b>VideoPortWrite</b><i>Xxx</i> directly; such addresses first must be mapped by calling <a href="display.videoportgetdevicebase">VideoPortGetDeviceBase</a>.

If the <i>ConfigurationData</i> buffer has no access range information and the miniport driver's <i>HwVidFindAdapter</i> function has not already called <a href="display.videoportgetbusdata">VideoPortGetBusData</a> (or <a href="display.videoportgetaccessranges">VideoPortGetAccessRanges</a>), its <i>HwVidQueryDeviceCallback</i> function can call <b>VideoPortGetBusData</b>. Access range information returned by <b>VideoPortGetBusData</b> also must be passed to <a href="display.videoportverifyaccessranges">VideoPortVerifyAccessRanges</a>.

If <b>VideoPortVerifyAccessRanges</b> returns NO_ERROR, the miniport driver can call <b>VideoPortGetDeviceBase</b> to obtain mapped logical addresses that it can use to communicate with the adapter by calling the <b>VideoPortRead</b><i>Xxx</i> and/or <b>VideoPortWrite</b><i>Xxx</i> functions.

If it cannot get bus-relative access ranges values by calling <b>VideoPortGetDeviceData</b>, <b>VideoPortGetBusData</b>, or <b>VideoPortGetAccessRanges</b>, a miniport driver can use a set of driver-supplied default access-range values to find its adapter. In these circumstances, the miniport driver must call <b>VideoPortVerifyAccessRanges</b> with the miniport driver-supplied access ranges, and, then call <b>VideoPortGetDeviceBase</b> only if <b>VideoPortVerifyAccessRanges</b> returned NO_ERROR. If a call to <b>VideoPortVerifyAccessRanges</b> is unsuccessful, a given bus-relative range is already in use by the driver of another device.

<i>HwVidQueryDeviceCallback</i> should be made pageable.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.videoportgetaccessranges">VideoPortGetAccessRanges</a>
</dt>
<dt>
<a href="display.videoportgetbusdata">VideoPortGetBusData</a>
</dt>
<dt>
<a href="display.videoportgetdevicebase">VideoPortGetDeviceBase</a>
</dt>
<dt>
<a href="display.videoportgetdevicedata">VideoPortGetDeviceData</a>
</dt>
<dt>
<a href="display.videoportverifyaccessranges">VideoPortVerifyAccessRanges</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PMINIPORT_QUERY_DEVICE_ROUTINE callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
