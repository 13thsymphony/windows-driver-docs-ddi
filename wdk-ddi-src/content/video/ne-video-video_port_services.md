---
UID: NE.video.VIDEO_PORT_SERVICES
title: VIDEO_PORT_SERVICES
author: windows-driver-content
description: The VIDEO_PORT_SERVICES enumerated type lists the interfaces that the video miniport driver can request from the video port driver by calling VideoPortQueryServices.
old-location: display\video_port_services.htm
old-project: display
ms.assetid: 3ca53536-e847-4c11-a28d-e046e8a392de
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: VIDEO_PORT_SERVICES, VIDEO_PORT_SERVICES
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
req.product: Windows 10 or later.
---

# VIDEO_PORT_SERVICES enumeration



## -description
The VIDEO_PORT_SERVICES enumerated type lists the interfaces that the video miniport driver can request from the video port driver by calling <a href="display.videoportqueryservices">VideoPortQueryServices</a>.



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

### -field VideoPortServicesAGP

Represents the AGP interface. 


### -field VideoPortServicesI2C

Represents the I2C interface. 


### -field VideoPortServicesHeadless

Represents the Headless interface. 


### -field VideoPortServicesInt10

Represents the Int10 interface. 


### -field VideoPortServicesDebugReport

Represents the Debug Report interface, which is available in the following operating systems:
 


<ul>
<li>Windows Server 2003 SP1 and subsequent service packs</li>
<li>Windows XP SP2 and subsequent service packs </li>
</ul>

### -field VideoPortServicesWCMemoryProtection

Represents the WC Memory Protection interface. 


## -remarks
Many functions are exported by the video port driver; the video miniport driver can call those functions using ordinary dynamic linking. Other functions implemented by the video port driver are not exported; instead, they are made available to the video miniport driver through function pointers. An interface, in this context, is a set of related function pointers. For example, the AGP interface is a set of pointers to functions (implemented by the video port driver) that provide AGP services to the video miniport driver.

The video miniport driver obtains a set of function pointers by passing a value from the VIDEO_PORT_SERVICES enumerated type to the <i>ServicesType</i> parameter of the <b>VideoPortQueryServices</b> function.


## -requirements
<table>
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
<a href="display.agp_functions_implemented_by_the_video_port_driver">AGP Functions Implemented by the Video Port Driver</a>
</dt>
<dt>
<a href="display.i2c_functions_implemented_by_the_video_port_driver">I2C Functions Implemented by the Video Port Driver</a>
</dt>
<dt>
<a href="display.int10_functions_implemented_by_the_video_port_driver">Int10 Functions Implemented by the Video Port Driver</a>
</dt>
<dt>
<a href="display.debug_report_functions_implemented_by_the_video_port_driver">Debug Report Functions Implemented by the Video Port Driver</a>
</dt>
<dt>
<a href="display.videoportqueryservices">VideoPortQueryServices</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_PORT_SERVICES enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

