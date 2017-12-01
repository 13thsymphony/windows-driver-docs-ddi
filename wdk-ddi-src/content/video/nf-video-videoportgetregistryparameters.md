---
UID: NF.video.VideoPortGetRegistryParameters
title: VideoPortGetRegistryParameters
author: windows-driver-content
description: The VideoPortGetRegistryParameters function retrieves device-specific configuration information under the adapter key in the registry at startup.
old-location: display\videoportgetregistryparameters.htm
old-project: display
ms.assetid: beca2e83-df56-4ed0-8ea8-b0090e574cd3
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: VideoPortGetRegistryParameters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VideoPortGetRegistryParameters
req.alt-loc: Videoprt.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# VideoPortGetRegistryParameters function



## -description
<p>The <b>VideoPortGetRegistryParameters</b> function retrieves device-specific configuration information under the<b> adapter </b>key in the registry at startup.</p>


## -syntax

````
VP_STATUS VideoPortGetRegistryParameters(
       PVOID                          HwDeviceExtension,
  _In_ PWSTR                          ParameterName,
       UCHAR                          IsParameterFileName,
       PMINIPORT_GET_REGISTRY_ROUTINE CallbackRoutine,
       PVOID                          Context
);
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> 

<dd>
<p>Pointer to the miniport driver's device extension.</p>
</dd>

### -param <i>ParameterName</i> [in]

<dd>
<p>Pointer to a NULL-terminated Unicode string that names the value entry to be retrieved from the registry. See the <b>Remarks</b> section for more information.</p>
</dd>

### -param <i>IsParameterFileName</i> 

<dd>
<p>If the value is <b>TRUE</b>, the data value normally returned is treated as a file name. In that case, the buffered contents of that file are returned, rather than the parameter itself.</p>
</dd>

### -param <i>CallbackRoutine</i> 

<dd>
<p>Pointer to the miniport driver's <a href="..\video\nc-video-pminiport-get-registry-routine.md">HwVidQueryNamedValueCallback</a> function.</p>
</dd>

### -param <i>Context</i> 

<dd>
<p>Pointer to a caller-determined context parameter to be passed to the <i>CallbackRoutine</i>, typically the <a href="..\video\ns-video--video-port-config-info.md">VIDEO_PORT_CONFIG_INFO</a> buffer.</p>
</dd>
</dl>

## -returns
<p><b>VideoPortGetRegistryParameters</b> returns NO_ERROR if it successfully collected the requested information and called the miniport driver's <i>HwVidQueryNamedValueCallback</i> function; otherwise returns ERROR_INVALID_PARAMETER.</p>

## -remarks
<p><b>VideoPortGetRegistryParameters</b> cannot be called from a miniport driver's <a href="..\video\nc-video-pvideo-hw-interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pvideo-hw-timer.md">HwVidTimer</a> functions, or from <a href="..\video\nf-video-videoportqueuedpc.md">VideoPortQueueDpc</a>, or from a callback to <a href="..\video\nf-video-videoportsynchronizeexecution.md">VideoPortSynchronizeExecution</a>.</p>

<p>For Windows XP and later operating system versions, the <i>ParameterName</i> parameter can contain a path that exactly references a value name one or more levels below the <b>adapter</b> key. For example, the string "SubKey1\Value1" can be used to obtain the value entry for the Value1 value number under the SubKey1 subkey. </p>

<p>The registry key from which <b>VideoPortGetRegistryParameters</b> retrieves configuration information cannot contain any information about the corresponding display driver, because miniport driver <a href="..\video\nc-video-pvideo-hw-find-adapter.md">HwVidFindAdapter</a> functions execute before any display driver is loaded.</p>

<p>Miniport drivers should not query configuration information stored in the <b>DefaultSettings</b> entries, which may not be supported in later versions of the operating system. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 2000 and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Videoprt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Videoprt.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\video\nc-video-pvideo-hw-find-adapter.md">HwVidFindAdapter</a>
</dt>
<dt>
<a href="..\video\nc-video-pvideo-hw-initialize.md">HwVidInitialize</a>
</dt>
<dt>
<a href="..\video\nc-video-pminiport-query-device-routine.md">HwVidQueryDeviceCallback</a>
</dt>
<dt>
<a href="..\video\nc-video-pminiport-get-registry-routine.md">HwVidQueryNamedValueCallback</a>
</dt>
<dt>
<a href="..\video\ns-video--video-port-config-info.md">VIDEO_PORT_CONFIG_INFO</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportgetdevicedata.md">VideoPortGetDeviceData</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportflushregistry.md">VideoPortFlushRegistry</a>
</dt>
<dt>
<a href="..\video\nf-video-videoportsetregistryparameters.md">VideoPortSetRegistryParameters</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortGetRegistryParameters function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
