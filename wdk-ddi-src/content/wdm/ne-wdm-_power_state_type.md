---
UID: NE:wdm._POWER_STATE_TYPE
title: _POWER_STATE_TYPE
author: windows-driver-content
description: The POWER_STATE_TYPE enumeration type indicates that a power state value is a system power state or a device power state.
old-location: kernel\power_state_type.htm
old-project: kernel
ms.assetid: d0e97474-4119-4359-a9f9-644c82df7fab
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _POWER_STATE_TYPE, POWER_STATE_TYPE, *PPOWER_STATE_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: POWER_STATE_TYPE
req.alt-loc: Wdm.h
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
req.typenames: POWER_STATE_TYPE, *PPOWER_STATE_TYPE
req.product: Windows 10 or later.
---

# _POWER_STATE_TYPE enumeration



## -description
The <b>POWER_STATE_TYPE</b> enumeration type indicates that a power state value is a system power state or a device power state.



## -syntax

````
typedef enum _POWER_STATE_TYPE { 
  SystemPowerState  = 0,
  DevicePowerState  = 1
} POWER_STATE_TYPE, *PPOWER_STATE_TYPE;
````


## -enum-fields

### -field SystemPowerState

Indicates a <a href="..\wdm\ne-wdm-_system_power_state.md">SYSTEM_POWER_STATE</a> value.


### -field DevicePowerState

Indicates a <a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a> value.


## -remarks
The <b>POWER_STATE_TYPE</b> enumeration type is used in conjunction with a value of type <a href="..\wdm\ns-wdm-_power_state.md">POWER_STATE</a> to indicate that the power state value is a system power state value or a device power state value. For an example, see <a href="..\wdm\nf-wdm-posetpowerstate.md">PoSetPowerState</a>.


## -see-also
<dl>
<dt>
<a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_power_state.md">POWER_STATE</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-posetpowerstate.md">PoSetPowerState</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm-_system_power_state.md">SYSTEM_POWER_STATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POWER_STATE_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

