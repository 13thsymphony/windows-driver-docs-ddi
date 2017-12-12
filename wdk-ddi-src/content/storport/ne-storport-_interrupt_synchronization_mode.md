---
UID: NE.storport._INTERRUPT_SYNCHRONIZATION_MODE
title: _INTERRUPT_SYNCHRONIZATION_MODE
author: windows-driver-content
description: The INTERRUPT_SYNCHRONIZATION_MODE enumerator specifies the interrupt synchronization mode.
old-location: storage\interrupt_synchronization_mode.htm
old-project: storage
ms.assetid: 964009ab-5f90-4f23-b22a-4c3e03d2449e
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _INTERRUPT_SYNCHRONIZATION_MODE, INTERRUPT_SYNCHRONIZATION_MODE
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
req.alt-api: INTERRUPT_SYNCHRONIZATION_MODE
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

# _INTERRUPT_SYNCHRONIZATION_MODE enumeration



## -description
The INTERRUPT_SYNCHRONIZATION_MODE enumerator specifies the interrupt synchronization mode.



## -syntax

````
typedef enum _INTERRUPT_SYNCHRONIZATION_MODE { 
  InterruptSupportNone            = 0,
  InterruptSynchronizeAll         = 1,
  InterruptSynchronizePerMessage  = 2
} INTERRUPT_SYNCHRONIZATION_MODE;
````


## -enum-fields

### -field InterruptSupportNone

MSI interrupts are not supported.


### -field InterruptSynchronizeAll

The Storport driver serializes all message signaled interrupts using a single interrupt spin lock. When an interrupt occurs, the Storport driver calls the miniport driver's <a href="storage.hwmsinterruptroutine">HwMSInterruptRoutine</a> routine at DIRQL after acquiring the interrupt spin lock.


### -field InterruptSynchronizePerMessage

The miniport driver serializes message signaled interrupts on a per message basis. In the synchronization per message mode, the Storport driver calls the miniport driver's <a href="storage.hwmsinterruptroutine">HwMSInterruptRoutine</a> routine at DIRQL   holding the interrupt spin lock of the corresponding  message. For more on the behavior of this synchronization mode, see the remarks section for HwMSInterruptRoutine.


## -remarks
Miniport drivers define the HBA's interrupt synchronization mode by assigning one of the INTERRUPT_SYNCHRONIZATION_MODE enumeration values to the <b>InterruptSynchronizationMode</b> member of the <a href="storage.port_configuration_information__storport_">PORT_CONFIGURATION_INFORMATION</a> structure. 


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
<a href="storage.hwmsinterruptroutine">HwMSInterruptRoutine</a>
</dt>
<dt>
<a href="storage.port_configuration_information__storport_">PORT_CONFIGURATION_INFORMATION</a>
</dt>
<dt>
<a href="storage.storportacquiremsispinlock">StorPortAcquireMSISpinLock</a>
</dt>
<dt>
<a href="storage.storportreleasemsispinlock">StorPortReleaseMSISpinLock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20INTERRUPT_SYNCHRONIZATION_MODE enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

