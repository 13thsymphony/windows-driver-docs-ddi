---
UID: NF.sensorscx.SENSOR_CONFIG_INIT
title: SENSOR_CONFIG_INIT
author: windows-driver-content
description: This function initializes a SENSOR_CONFIG structure.
old-location: sensors\sensor_config_init.htm
old-project: sensors
ms.assetid: 0A7189A0-1375-4456-B8A5-D92E0AA74A99
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: SENSOR_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sensorscx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SENSOR_CONFIG_INIT
req.alt-loc: SensorsCx.h
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

# SENSOR_CONFIG_INIT function



## -description
<p>This function initializes a <a href="..\sensorscx\ns-sensorscx--sensor-config.md">SENSOR_CONFIG</a> structure.</p>


## -syntax

````
FORCEINLINE VOID SENSOR_CONFIG_INIT(
  _Out_ PSENSOR_CONFIG pConfig
);
````


## -parameters
<dl>

### -param pConfig [out]

<dd>
<p>A pointer to a new <a href="..\sensorscx\ns-sensorscx--sensor-config.md">SENSOR_CONFIG</a> structure.</p>
</dd>
</dl>

## -returns
<p>This function does not return a value.</p>

## -remarks


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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>SensorsCx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\sensorscx\ns-sensorscx--sensor-config.md">SENSOR_CONFIG</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20SENSOR_CONFIG_INIT function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
