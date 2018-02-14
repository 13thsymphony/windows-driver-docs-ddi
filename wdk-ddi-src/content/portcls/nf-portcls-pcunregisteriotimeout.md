---
UID: NF:portcls.PcUnregisterIoTimeout
title: PcUnregisterIoTimeout function
author: windows-driver-content
description: The PcUnregisterIoTimeout function unregisters a driver-supplied I/O-timer callback routine for a specified device object.
old-location: audio\pcunregisteriotimeout.htm
old-project: audio
ms.assetid: 4266c775-a2e9-46f0-91ad-6f6cce06bea0
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audpc-routines_cb67c1bb-c5ad-4118-bdff-906735214653.xml, audio.pcunregisteriotimeout, PcUnregisterIoTimeout, portcls/PcUnregisterIoTimeout, PcUnregisterIoTimeout function [Audio Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcUnregisterIoTimeout function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Portcls.lib
-	Portcls.dll
apiname:
-	PcUnregisterIoTimeout
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---


# PcUnregisterIoTimeout function
The <b>PcUnregisterIoTimeout</b> function unregisters a driver-supplied I/O-timer callback routine for a specified device object.
<div class="alert"><b>Note</b>  This function is deprecated for Windows 8 and later versions of Windows.  For Windows on Arm systems, this function is commented out in the PortCls class driver and is inaccessible.</div><div> </div>

## Syntax

````
NTSTATUS PcUnregisterIoTimeout(
  _In_ PDEVICE_OBJECT    pDeviceObject,
  _In_ PIO_TIMER_ROUTINE pTimerRoutine,
  _In_ PVOID             pContext
);
````

## Parameters

`pDeviceObject`

Pointer to the same device object that the driver supplied when it previously called <a href="..\portcls\nf-portcls-pcregisteriotimeout.md">PcRegisterIoTimeout</a>. The device object is a system structure of type <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>.

`pTimerRoutine`

Pointer to the same I/O-timer callback routine that the driver supplied when it previously called <a href="..\portcls\nf-portcls-pcregisteriotimeout.md">PcRegisterIoTimeout</a>

`pContext`

Pointer to the same driver-determined context that the driver supplied when it previously called <a href="..\portcls\nf-portcls-pcregisteriotimeout.md">PcRegisterIoTimeout</a>


## Return Value

<b>PcUnregisterIoTimeout</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code. The following table shows some of the possible error codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
Indicates that no timer callback with the same device object, callback routine, and context is currently registered.

</td>
</tr>
</table>

## Remarks

This call succeeds only if a time-out callback with the same device object, timer routine, and context was previously registered with a call to the <a href="..\portcls\nf-portcls-pcregisteriotimeout.md">PcRegisterIoTimeout</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | The PortCls system driver implements the PcUnregisterIoTimeout function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems. The PortCls system driver implements the PcUnregisterIoTimeout function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems. |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | Portcls.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\portcls\nf-portcls-pcregisteriotimeout.md">PcRegisterIoTimeout</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcUnregisterIoTimeout function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>