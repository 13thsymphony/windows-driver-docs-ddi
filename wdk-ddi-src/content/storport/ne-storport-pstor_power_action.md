---
UID: NE.storport.PSTOR_POWER_ACTION
title: PSTOR_POWER_ACTION
author: windows-driver-content
description: The STOR_POWER_ACTION enumerator indicates the power state that the system is about to enter during a power transition.
old-location: storage\stor_power_action.htm
old-project: storage
ms.assetid: ffc7c1ec-faec-4383-ab69-844cf68d054f
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PSTOR_POWER_ACTION, STOR_POWER_ACTION, *PSTOR_POWER_ACTION
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
req.alt-api: STOR_POWER_ACTION
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

# PSTOR_POWER_ACTION enumeration



## -description
The STOR_POWER_ACTION enumerator indicates the power state that the system is about to enter during a power transition. 


## -syntax

````
typedef enum  { 
  StorPowerActionNone           = 0,
  StorPowerActionReserved       = 1,
  StorPowerActionSleep          = 2,
  StorPowerActionHibernate      = 3,
  StorPowerActionShutdown       = 4,
  StorPowerActionShutdownReset  = 5,
  StorPowerActionShutdownOff    = 6,
  StorPowerActionWarmEject      = 7
} STOR_POWER_ACTION, *PSTOR_POWER_ACTION;
````


## -enum-fields

### -field StorPowerActionNone

No system shutdown is about to occur.

### -field StorPowerActionReserved

Reserved.

### -field StorPowerActionSleep

The system is entering standby.

### -field StorPowerActionHibernate

The system is entering hibernation.

### -field StorPowerActionShutdown

The system is shutting down, but the type of shutdown is not known.

### -field StorPowerActionShutdownReset

The system is shutting down and resetting.

### -field StorPowerActionShutdownOff

The system is shutting down and powering off.

### -field StorPowerActionWarmEject

The system is preparing for ejection.

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
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_POWER_ACTION enumeration%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
