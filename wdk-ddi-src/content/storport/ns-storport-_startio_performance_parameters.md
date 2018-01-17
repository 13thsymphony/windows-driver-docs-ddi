---
UID: NS:storport._STARTIO_PERFORMANCE_PARAMETERS
title: _STARTIO_PERFORMANCE_PARAMETERS
author: windows-driver-content
description: The STARTIO_PERFORMANCE_PARAMETERS structure describes the performance parameters that are returned to the miniport driver by the StorPortGetStartIoPerfParams routine.
old-location: storage\startio_performance_parameters.htm
old-project: storage
ms.assetid: 984a8584-ebdd-4e93-868b-1537a3615c1b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _STARTIO_PERFORMANCE_PARAMETERS, *PSTARTIO_PERFORMANCE_PARAMETERS, STARTIO_PERFORMANCE_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STARTIO_PERFORMANCE_PARAMETERS
req.alt-loc: storport.h
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
req.typenames: *PSTARTIO_PERFORMANCE_PARAMETERS, STARTIO_PERFORMANCE_PARAMETERS
req.product: Windows 10 or later.
---

# _STARTIO_PERFORMANCE_PARAMETERS structure



## -description
The <b>STARTIO_PERFORMANCE_PARAMETERS</b> structure describes the performance parameters that are returned to the miniport driver by the <a href="..\storport\nf-storport-storportgetstartioperfparams.md">StorPortGetStartIoPerfParams</a> routine.



## -syntax

````
typedef struct _STARTIO_PERFORMANCE_PARAMETERS {
  ULONG Version;
  ULONG Size;
  ULONG MessageNumber;
  ULONG ChannelNumber;
} STARTIO_PERFORMANCE_PARAMETERS, *PSTARTIO_PERFORMANCE_PARAMETERS;
````


## -struct-fields

### -field Version

The version number of the structure. This member is valid starting with Windows 8.


### -field Size

The size of the structure.


### -field MessageNumber

The offset in the device's MSI-X table for the optimal MSI-X message with which to interrupt. If the device does not support MSI-X messages, this member will be zero.


### -field ChannelNumber

Denotes the concurrent channel in which Storport is passing the I/O. If the miniport driver did not set up concurrent channels, this member will be zero.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\storport\nf-storport-storportgetstartioperfparams.md">StorPortGetStartIoPerfParams</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STARTIO_PERFORMANCE_PARAMETERS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

