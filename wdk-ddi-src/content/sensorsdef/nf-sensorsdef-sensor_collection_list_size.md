---
UID: NF:sensorsdef.SENSOR_COLLECTION_LIST_SIZE
title: SENSOR_COLLECTION_LIST_SIZE function
author: windows-driver-content
description: This function returns the size of a SENSOR_COLLECTION_LIST structure.
old-location: sensors\sensor_collection_list_size.htm
old-project: sensors
ms.assetid: 98191F02-E047-41BC-922F-867DED522E59
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SENSOR_COLLECTION_LIST_SIZE
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
req.alt-api: SENSOR_COLLECTION_LIST_SIZE
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
req.typenames: SENSOR_STATE
req.product: Windows 10 or later.
---

# SENSOR_COLLECTION_LIST_SIZE function



## -description
This function returns the size of a <a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a> structure. 



## -syntax

````
FORCEINLINE ULONG SENSOR_COLLECTION_LIST_SIZE(
  _In_ ULONG Count
);
````


## -parameters

### -param Count [in]

The number of <a href="..\sensorsdef\ns-sensorsdef-sensor_value_pair.md">SENSOR_VALUE_PAIR</a> elements in the <a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a>.


## -returns
The <b>SENSOR_COLLECTION_LIST_SIZE</b> function returns a ULONG value that represents the size of the list of sensor-value pairs.


## -remarks


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
<dt>Sensorsdef.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20SENSOR_COLLECTION_LIST_SIZE function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

