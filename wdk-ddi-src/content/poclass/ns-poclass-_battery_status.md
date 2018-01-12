---
UID: NS:poclass._BATTERY_STATUS
title: _BATTERY_STATUS
author: windows-driver-content
description: The BATTERY_STATUS structure is used by battery miniclass drivers to return status information in response to a call to BatteryMiniQueryStatus.
old-location: battery\battery_status.htm
old-project: battery
ms.assetid: 48df787b-f9f6-45d1-872c-ceeda3087af6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _BATTERY_STATUS, *PBATTERY_STATUS, BATTERY_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: poclass.h
req.include-header: Batclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BATTERY_STATUS
req.alt-loc: poclass.h
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
req.typenames: *PBATTERY_STATUS, BATTERY_STATUS
---

# _BATTERY_STATUS structure



## -description
The BATTERY_STATUS structure is used by battery miniclass drivers to return status information in response to a call to <a href="https://msdn.microsoft.com/04811f63-8a57-4b39-84c5-c9b7f803c057">BatteryMiniQueryStatus</a>.



## -syntax

````
typedef struct _BATTERY_STATUS {
  ULONG PowerState;
  ULONG Capacity;
  ULONG Voltage;
  LONG  Rate;
} BATTERY_STATUS, *PBATTERY_STATUS;
````


## -struct-fields

### -field PowerState

Specifies a battery power state as one or more of the following flags, ORed together: BATTERY_POWER_ON_LINE, BATTERY_DISCHARGING, BATTERY_CHARGING, and BATTERY_CRITICAL. 


### -field Capacity

Specifies the capacity of the given battery, in milliwatt-hours, or BATTERY_UNKNOWN_CAPACITY if the capacity cannot be determined.


### -field Voltage

Specifies the voltage, in millivolts, across the terminals of the given battery, or BATTERY_UNKNOWN_VOLTAGE if the voltage cannot be determined.


### -field Rate

Specifies the current rate of battery usage in milliwatts or, if the driver reports relative capacity, in units per hour. A positive value means that the battery is charging; a negative value means the battery is discharging. If the driver cannot determine the rate, it should return BATTERY_UNKNOWN_RATE.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Poclass.h (include Batclass.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/04811f63-8a57-4b39-84c5-c9b7f803c057">BatteryMiniQueryStatus</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [battery\battery]:%20BATTERY_STATUS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

