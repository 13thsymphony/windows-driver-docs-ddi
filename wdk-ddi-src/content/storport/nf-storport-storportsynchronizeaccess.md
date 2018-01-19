---
UID : NF:storport.StorPortSynchronizeAccess
title : StorPortSynchronizeAccess function
author : windows-driver-content
description : The StorPortSynchronizeAccess routine provides synchronized access to a miniport driver's device extension.
old-location : storage\storportsynchronizeaccess.htm
old-project : storage
ms.assetid : eece67ed-faff-4166-8fa0-d501df9c1363
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : StorPortSynchronizeAccess
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : storport.h
req.include-header : Storport.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : StorPortSynchronizeAccess
req.alt-loc : Storport.lib,Storport.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Storport.lib
req.dll : 
req.irql : 
req.typenames : STOR_SPINLOCK
req.product : Windows 10 or later.
---


# StorPortSynchronizeAccess function
The <b>StorPortSynchronizeAccess</b> routine provides synchronized access to a miniport driver's device extension.

## Syntax

````
STORPORT_API BOOLEAN StorPortSynchronizeAccess(
  _In_     PVOID                     HwDeviceExtension,
  _In_     PSTOR_SYNCHRONIZED_ACCESS SynchronizedAccessRoutine,
  _In_opt_ PVOID                     Context
);
````

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. The port driver frees this memory when it removes the device.

`SynchronizedAccessRoutine`

Pointer to a caller-supplied routine whose execution is to be synchronized with the execution of the ISR associated with the interrupt objects. For a prototype of this routine, see the Remarks section later in this topic.

`Context`

Pointer to a context area to be passed to the caller-supplied callback routine when it is called.


## Return Value

The return value from  <i>SynchronizedAccessRoutine</i>.

## Remarks

Miniport drivers that operate in full-duplex mode, and that access information that is shared between their <a href="..\storport\nc-storport-hw_startio.md">HwStorStartIo</a> routine and interrupt-service routine, must use this routine to access the shared data in a synchronized manner. 

The miniport driver passes a callback routine to <b>StorPortSynchronizeAccess</b>, and <b>StorPortSynchronizeAccess</b> calls it after guaranteeing exclusive access to sensitive data structures. The miniport driver's callback routine must conform to the following prototype:

where <i>HwDeviceExtension</i> is a pointer to the hardware device extension, and <i>Context</i> is just a pointer to the same context information that the caller supplied when calling <b>StorPortSynchronizeAccess</b>. 

For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/storage/synchronized-access-within-unsynchronized-miniport-driver-routines">Synchronized Access within Unsynchronized Miniport Driver Routines</a>.

For more information about synchronization routines, see <a href="..\wdm\nf-wdm-kesynchronizeexecution.md">KeSynchronizeExecution</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | storport.h (include Storport.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-kesynchronizeexecution.md">KeSynchronizeExecution</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortSynchronizeAccess routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>