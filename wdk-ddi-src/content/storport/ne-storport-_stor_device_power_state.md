---
UID: NE.storport._STOR_DEVICE_POWER_STATE
title: _STOR_DEVICE_POWER_STATE
author: windows-driver-content
description: The STOR_DEVICE_POWER_STATE enumerator specifies a device power state.
old-location: storage\stor_device_power_state.htm
old-project: storage
ms.assetid: 563ece3e-1359-4e3c-9ae7-61b94bf90ad0
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _STOR_DEVICE_POWER_STATE, PSTOR_DEVICE_POWER_STATE, STOR_DEVICE_POWER_STATE, *PSTOR_DEVICE_POWER_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STOR_DEVICE_POWER_STATE
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
req.product: Windows 10 or later.
---

# _STOR_DEVICE_POWER_STATE enumeration



## -description
The STOR_DEVICE_POWER_STATE enumerator specifies a device power state.



## -syntax

````
typedef enum _STOR_DEVICE_POWER_STATE { 
  StorPowerDeviceUnspecified  = 0,
  StorPowerDeviceD0           = 1,
  StorPowerDeviceD1           = 2,
  StorPowerDeviceD2           = 3,
  StorPowerDeviceD3           = 4,
  StorPowerDeviceMaximum      = 5
} STOR_DEVICE_POWER_STATE, *PSTOR_DEVICE_POWER_STATE;
````


## -enum-fields

### -field StorPowerDeviceUnspecified

Device power state unspecified.


### -field StorPowerDeviceD0

The D0 device power state.


### -field StorPowerDeviceD1

The D1 device power state.


### -field StorPowerDeviceD2

The D2 device power state.


### -field StorPowerDeviceD3

The D3 device power state.


### -field StorPowerDeviceMaximum

The upper delimiting value on device power states.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.scsi_power_request_block">SCSI_POWER_REQUEST_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_DEVICE_POWER_STATE enumeration%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

