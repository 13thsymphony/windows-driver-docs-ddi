---
UID: NS.drmk.tagDRMFORWARD
title: tagDRMFORWARD
author: windows-driver-content
description: The DRMFORWARD structure contains the information that the DRMK system driver needs in order to forward a DRM content ID to a device that handles protected content.
old-location: audio\drmforward.htm
old-project: audio
ms.assetid: 30e2e62a-3ae4-4efe-a6e9-6aece6bfbb46
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: tagDRMFORWARD, DRMFORWARD, *PDRMFORWARD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: drmk.h
req.include-header: Drmk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DRMFORWARD
req.alt-loc: drmk.h
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
req.iface: IDrmAudioStream
---

# tagDRMFORWARD structure



## -description
<p>The DRMFORWARD structure contains the information that the <a href="audio.kernel_mode_wdm_audio_components#drmk_system_driver#drmk_system_driver">DRMK system driver</a> needs in order to forward a DRM content ID to a device that handles protected content.</p>


## -syntax

````
typedef struct tagDRMFORWARD {
  DWORD          Flags;
  PDEVICE_OBJECT DeviceObject;
  PFILE_OBJECT   FileObject;
  PVOID          Context;
} DRMFORWARD, *PDRMFORWARD;
````


## -struct-fields
<dl>

### -field <b>Flags</b>

<dd>
<p>No flag bits are currently defined. Set this member to zero.</p>
</dd>

### -field <b>DeviceObject</b>

<dd>
<p>Pointer to the device object, which is a system structure of type <a href="..\wdm\ns-wdm--device-object.md">DEVICE_OBJECT</a>.</p>
</dd>

### -field <b>FileObject</b>

<dd>
<p>Pointer to the file object, which is a system structure of type <a href="..\wdm\ns-wdm--file-object.md">FILE_OBJECT</a>.</p>
</dd>

### -field <b>Context</b>

<dd>
<p>Pointer to context data. For more information, see the following Remarks section.</p>
</dd>
</dl>

## -remarks
<p>This structure is one of the <a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a> function's call parameters. The structure contains the information that the function needs to send a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>set-property request to a WDM driver.</p>

<p>The WDM driver manages the device that is represented by the <b>DeviceObject</b> member. The <b>DrmForwardContentToDeviceObject</b> function sends the property request to this device object.</p>

<p>When constructing the IRP that contains the property request, the <b>DrmForwardContentToDeviceObject</b> function copies the <b>FileObject</b> member into the <b>FileObject</b> field in the driver's I/O stack location in the IRP. If the WDM driver is a KS driver (which implements all or part of a KS filter), the <b>FileObject</b> member represents the pin on the filter that is to receive the stream containing the protected content. For a non-KS driver, the context fields in the FILE_OBJECT structure can contain any value whose meaning is agreed upon between the driver and the caller of the <b>DrmForwardContentToDeviceObject</b> function.</p>

<p>The <b>Context</b> member contains a context value that the <b>DrmForwardContentToDeviceObject</b> function copies into the property descriptor of the KSPROPERTY_DRMAUDIOSTREAM_CONTENTID set-property request (the <a href="audio.ksp_drmaudiostream_contentid">KSP_DRMAUDIOSTREAM_CONTENTID</a> structure's <b>Context</b> member). The <b>Context</b> member can contain any value whose meaning is agreed upon between the driver and the caller of the <b>DrmForwardContentToDeviceObject</b> function.</p>

<p>By convention, if the downstream module is a KS filter, the <b>Context</b> member points to a file object that specifies the KS pin to which the <b>DrmForwardContentToDeviceObject</b> function sends the property request. In other words, the <b>Context</b> member points to the same file object as the <b>FileObject</b> member.</p>

<p>The DRMFORWARD structure is also used by the <a href="..\portcls\nf-portcls-pcforwardcontenttodeviceobject.md">PcForwardContentToDeviceObject</a> function and the <a href="audio.idrmport2_forwardcontenttodeviceobject">IDrmPort2::ForwardContentToDeviceObject</a> method, which are alternative entry points for the <b>DrmForwardContentToDeviceObject</b> function. For more information, see <a href="NULL">DRM Functions and Interfaces</a>.</p>

<p>When an audio driver forwards DRM content to a system-supplied USB driver, the following conditions apply: <ul>
<li><b>DRMFORWARD.DeviceObject</b> must be placed at the top of the device stack.</li>
<li><b>DRMFORWARD.FileObject</b> can be <b>NULL</b> because the USB stack does not use IO_STACK_LOCATION.FileObject.</li>
<li><b>DRMFORWARD.Context</b> must be set to a USBD_PIPE_HANDLE value that corresponds to the pipe used by the audio driver.</li>
</ul>
</p>

<p>For general information about DRM, see <a href="NULL">Digital Rights Management</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Drmk.h (include Drmk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm--device-object.md">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--file-object.md">FILE_OBJECT</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmforwardcontenttodeviceobject.md">DrmForwardContentToDeviceObject</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537351">KSPROPERTY_DRMAUDIOSTREAM_CONTENTID</a>
</dt>
<dt>
<a href="audio.ksp_drmaudiostream_contentid">KSP_DRMAUDIOSTREAM_CONTENTID</a>
</dt>
<dt>
<a href="..\portcls\nf-portcls-pcforwardcontenttodeviceobject.md">PcForwardContentToDeviceObject</a>
</dt>
<dt>
<a href="audio.idrmport2_forwardcontenttodeviceobject">IDrmPort2::ForwardContentToDeviceObject</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20DRMFORWARD structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
