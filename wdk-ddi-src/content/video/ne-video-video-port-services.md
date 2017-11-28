---
UID: NE.video.VIDEO_PORT_SERVICES
title: VIDEO_PORT_SERVICES
author: windows-driver-content
description: The VIDEO_PORT_SERVICES enumerated type lists the interfaces that the video miniport driver can request from the video port driver by calling VideoPortQueryServices.
old-location: display\video_port_services.htm
old-project: display
ms.assetid: 3ca53536-e847-4c11-a28d-e046e8a392de
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: VHF_CONFIG, VHF_CONFIG, *PVHF_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: video.h
req.include-header: Video.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VIDEO_PORT_SERVICES
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
req.iface: 
req.product: Windows 10 or later.
---

# VIDEO_PORT_SERVICES enumeration



## -description
<p>The VIDEO_PORT_SERVICES enumerated type lists the interfaces that the video miniport driver can request from the video port driver by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a>.</p>


## -syntax

````
typedef enum  { 
  VideoPortServicesAGP                 = 1,
  VideoPortServicesI2C,
  VideoPortServicesHeadless,
  VideoPortServicesInt10,
  VideoPortServicesDebugReport,
  VideoPortServicesWCMemoryProtection
} VIDEO_PORT_SERVICES;
````


## -enum-fields
<dl>

### -field <a id="VideoPortServicesAGP"></a><a id="videoportservicesagp"></a><a id="VIDEOPORTSERVICESAGP"></a><b>VideoPortServicesAGP</b>

<dd>
<p>Represents the AGP interface. </p>
</dd>

### -field <a id="VideoPortServicesI2C"></a><a id="videoportservicesi2c"></a><a id="VIDEOPORTSERVICESI2C"></a><b>VideoPortServicesI2C</b>

<dd>
<p>Represents the I2C interface. </p>
</dd>

### -field <a id="VideoPortServicesHeadless"></a><a id="videoportservicesheadless"></a><a id="VIDEOPORTSERVICESHEADLESS"></a><b>VideoPortServicesHeadless</b>

<dd>
<p>Represents the Headless interface. </p>
</dd>

### -field <a id="VideoPortServicesInt10"></a><a id="videoportservicesint10"></a><a id="VIDEOPORTSERVICESINT10"></a><b>VideoPortServicesInt10</b>

<dd>
<p>Represents the Int10 interface. </p>
</dd>

### -field <a id="VideoPortServicesDebugReport"></a><a id="videoportservicesdebugreport"></a><a id="VIDEOPORTSERVICESDEBUGREPORT"></a><b>VideoPortServicesDebugReport</b>

<dd>
<p>Represents the Debug Report interface, which is available in the following operating systems:
 
</p>
<ul>
<li>Windows Server 2003 SP1 and subsequent service packs</li>
<li>Windows XP SP2 and subsequent service packs </li>
</ul>
</dd>

### -field <a id="VideoPortServicesWCMemoryProtection"></a><a id="videoportserviceswcmemoryprotection"></a><a id="VIDEOPORTSERVICESWCMEMORYPROTECTION"></a><b>VideoPortServicesWCMemoryProtection</b>

<dd>
<p>Represents the WC Memory Protection interface. </p>
</dd>
</dl>

## -remarks
<p>Many functions are exported by the video port driver; the video miniport driver can call those functions using ordinary dynamic linking. Other functions implemented by the video port driver are not exported; instead, they are made available to the video miniport driver through function pointers. An interface, in this context, is a set of related function pointers. For example, the AGP interface is a set of pointers to functions (implemented by the video port driver) that provide AGP services to the video miniport driver.</p>

<p>The video miniport driver obtains a set of function pointers by passing a value from the VIDEO_PORT_SERVICES enumerated type to the <i>ServicesType</i> parameter of the <b>VideoPortQueryServices</b> function.</p>

<p>Many functions are exported by the video port driver; the video miniport driver can call those functions using ordinary dynamic linking. Other functions implemented by the video port driver are not exported; instead, they are made available to the video miniport driver through function pointers. An interface, in this context, is a set of related function pointers. For example, the AGP interface is a set of pointers to functions (implemented by the video port driver) that provide AGP services to the video miniport driver.</p>

<p>The video miniport driver obtains a set of function pointers by passing a value from the VIDEO_PORT_SERVICES enumerated type to the <i>ServicesType</i> parameter of the <b>VideoPortQueryServices</b> function.</p>

<p>Many functions are exported by the video port driver; the video miniport driver can call those functions using ordinary dynamic linking. Other functions implemented by the video port driver are not exported; instead, they are made available to the video miniport driver through function pointers. An interface, in this context, is a set of related function pointers. For example, the AGP interface is a set of pointers to functions (implemented by the video port driver) that provide AGP services to the video miniport driver.</p>

<p>The video miniport driver obtains a set of function pointers by passing a value from the VIDEO_PORT_SERVICES enumerated type to the <i>ServicesType</i> parameter of the <b>VideoPortQueryServices</b> function.</p>

## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538227">AGP Functions Implemented by the Video Port Driver</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567384">I2C Functions Implemented by the Video Port Driver</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567732">Int10 Functions Implemented by the Video Port Driver</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551792">Debug Report Functions Implemented by the Video Port Driver</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_PORT_SERVICES enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
