---
UID: NE.iddcx.IDDCX_MONITOR_MODE_ORIGIN
title: IDDCX_MONITOR_MODE_ORIGIN
author: windows-driver-content
description: Used to describe a mode the monitor supports based on the monitor description.
old-location: display\iddcx_monitor_mode_origin.htm
old-project: display
ms.assetid: 96aac09b-c6fc-43a7-a6d8-36f642e0f5d7
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IDDCX_MONITOR_MODE_ORIGIN,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDDCX_MONITOR_MODE_ORIGIN
req.alt-loc: iddcx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _requires_same_
---

# IDDCX_MONITOR_MODE_ORIGIN enumeration



## -description

                     Used to describe a mode the monitor supports based on the monitor description.
                



## -syntax

````
typedef enum _IDDCX_MONITOR_MODE_ORIGIN { 
  IDDCX_MONITOR_MODE_ORIGIN_UNINITIALIZED      = 0,
  IDDCX_MONITOR_MODE_ORIGIN_MONITORDESCRIPTOR  = 1,
  IDDCX_MONITOR_MODE_ORIGIN_DRIVER             = 2
} IDDCX_MONITOR_MODE_ORIGIN;
````


## -enum-fields

### -field IDDCX_MONITOR_MODE_ORIGIN_UNINITIALIZED


                        
                    Indicates that an <b>IDDCX_MONITOR_MODE_ORIGIN</b> variable has not yet been assigned a meaningful value.


### -field IDDCX_MONITOR_MODE_ORIGIN_MONITORDESCRIPTOR


                        Indicates that the driver added this mode from directly processing the monitor description
                    


### -field IDDCX_MONITOR_MODE_ORIGIN_DRIVER


                        Indicates that the driver did not add this mode as a direct resolution of processing the modes/ supported by the monitor but because of separate additional knowledge it has about the monitor
                    


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>