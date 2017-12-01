---
UID: NF.sensorsdef.SENSOR_PROPERTY_LIST_SIZE
title: SENSOR_PROPERTY_LIST_SIZE
author: windows-driver-content
description: This function returns the size of the property list.
old-location: sensors\sensor_property_list_size.htm
old-project: sensors
ms.assetid: 17B53AAF-5027-4E45-ABAF-566771DDF1DE
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: SENSOR_PROPERTY_LIST_SIZE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sensorsdef.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SENSOR_PROPERTY_LIST_SIZE
req.alt-loc: Sensorsdef.h
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

# SENSOR_PROPERTY_LIST_SIZE function



## -description
<p>This function returns the size of the property list.</p>


## -syntax

````
FORCEINLINE ULONG SENSOR_PROPERTY_LIST_SIZE(
  _In_ ULONG Count
);
````


## -parameters
<dl>

### -param <i>Count</i> [in]

<dd>
<p>The number of PROPERTYKEY elements.</p>
</dd>
</dl>

## -returns
<p>The <b>SENSOR_PROPERTY_LIST_SIZE</b> function returns a ULONG value that represents the size of the property list.</p>

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
<dt>Sensorsdef.h</dt>
</dl>
</td>
</tr>
</table>