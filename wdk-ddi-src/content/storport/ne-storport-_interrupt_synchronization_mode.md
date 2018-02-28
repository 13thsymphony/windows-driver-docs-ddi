---
UID: NE:storport._INTERRUPT_SYNCHRONIZATION_MODE
title: "_INTERRUPT_SYNCHRONIZATION_MODE"
author: windows-driver-content
description: The INTERRUPT_SYNCHRONIZATION_MODE enumerator specifies the interrupt synchronization mode.
old-location: storage\interrupt_synchronization_mode.htm
old-project: storage
ms.assetid: 964009ab-5f90-4f23-b22a-4c3e03d2449e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: INTERRUPT_SYNCHRONIZATION_MODE, INTERRUPT_SYNCHRONIZATION_MODE enumeration [Storage Devices], InterruptSupportNone, InterruptSynchronizeAll, InterruptSynchronizePerMessage, _INTERRUPT_SYNCHRONIZATION_MODE, storage.interrupt_synchronization_mode, storport/INTERRUPT_SYNCHRONIZATION_MODE, storport/InterruptSupportNone, storport/InterruptSynchronizeAll, storport/InterruptSynchronizePerMessage, structs-storport_036aa424-5b04-4bf5-8418-8da008834c5b.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	INTERRUPT_SYNCHRONIZATION_MODE
product: Windows
targetos: Windows
req.typenames: INTERRUPT_SYNCHRONIZATION_MODE
req.product: Windows 10 or later.
---

# _INTERRUPT_SYNCHRONIZATION_MODE Enumeration
The INTERRUPT_SYNCHRONIZATION_MODE enumerator specifies the interrupt synchronization mode.

## Syntax
````
typedef enum _INTERRUPT_SYNCHRONIZATION_MODE { 
  InterruptSupportNone            = 0,
  InterruptSynchronizeAll         = 1,
  InterruptSynchronizePerMessage  = 2
} INTERRUPT_SYNCHRONIZATION_MODE;
````

## Constants

<table>
            
                <tr>
                    <td>InterruptSupportNone</td>
                    <td>MSI interrupts are not supported.</td>
                </tr>
            
                <tr>
                    <td>InterruptSynchronizeAll</td>
                    <td>The Storport driver serializes all message signaled interrupts using a single interrupt spin lock. When an interrupt occurs, the Storport driver calls the miniport driver's <a href="..\storport\nc-storport-hw_message_signaled_interrupt_routine.md">HwMSInterruptRoutine</a> routine at DIRQL after acquiring the interrupt spin lock.</td>
                </tr>
            
                <tr>
                    <td>InterruptSynchronizePerMessage</td>
                    <td>The miniport driver serializes message signaled interrupts on a per message basis. In the synchronization per message mode, the Storport driver calls the miniport driver's <a href="..\storport\nc-storport-hw_message_signaled_interrupt_routine.md">HwMSInterruptRoutine</a> routine at DIRQL   holding the interrupt spin lock of the corresponding  message. For more on the behavior of this synchronization mode, see the remarks section for HwMSInterruptRoutine.</td>
                </tr>
</table>

## Remarks

Miniport drivers define the HBA's interrupt synchronization mode by assigning one of the INTERRUPT_SYNCHRONIZATION_MODE enumeration values to the <b>InterruptSynchronizationMode</b> member of the <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | storport.h (include Storport.h) |

## See Also

<a href="..\storport\nc-storport-hw_message_signaled_interrupt_routine.md">HwMSInterruptRoutine</a>



<a href="..\storport\nf-storport-storportacquiremsispinlock.md">StorPortAcquireMSISpinLock</a>



<a href="..\storport\nf-storport-storportreleasemsispinlock.md">StorPortReleaseMSISpinLock</a>



<a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20INTERRUPT_SYNCHRONIZATION_MODE enumeration%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>