---
UID: NF:wmilib.WmiCompleteRequest
title: WmiCompleteRequest function
author: windows-driver-content
description: The WmiCompleteRequest routine indicates that a driver has finished processing a WMI request in a DpWmiXxx routine.
old-location: kernel\wmicompleterequest.htm
old-project: kernel
ms.assetid: c6377dcc-a83b-4766-b882-25d228a26efe
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: WmiCompleteRequest, WmiCompleteRequest routine [Kernel-Mode Driver Architecture], k902_08bc200c-67e2-4806-b744-621f31ec6af3.xml, kernel.wmicompleterequest, wmilib/WmiCompleteRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wmilib.h
req.include-header: Wmilib.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: Wmilib.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wmilib.lib
-	Wmilib.dll
api_name:
-	WmiCompleteRequest
product: Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---


# WmiCompleteRequest function
The <b>WmiCompleteRequest</b> routine indicates that a driver has finished processing a WMI request in a <i>DpWmiXxx</i> routine.

## Syntax

```
NTSTATUS WmiCompleteRequest(
  PDEVICE_OBJECT DeviceObject,
  PIRP           Irp,
  NTSTATUS       Status,
  ULONG          BufferUsed,
  CCHAR          PriorityBoost
);
```

## Parameters

`DeviceObject`

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>.

`Irp`

A pointer to the IRP.

`Status`

Specifies the status to return for the IRP.

`BufferUsed`

Specifies the number of bytes needed in the buffer passed to the driver's <i>DpWmiXxx</i> routine. If the buffer is too small, the driver sets <i>Status</i> to STATUS_BUFFER_TOO_SMALL and sets <i>BufferUsed</i> to the number of bytes needed for the data to be returned. If the buffer passed is large enough, the driver sets <i>BufferUsed</i> to the number of bytes actually used.

`PriorityBoost`

Specifies a system-defined constant by which to increment the run-time priority of the original thread that requested the operation. WMI calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff548343">IoCompleteRequest</a> with <i>PriorityBoost</i> when it completes the IRP. See <b>IoCompleteRequest</b> for more information on <i>PriorityBoost</i>.


## Return Value

<b>WmiCompleteRequest</b> returns the value that was passed to it in the <i>Status</i> parameter unless <i>Status</i> was set to STATUS_BUFFER_TOO_SMALL.  If the driver set <i>Status</i> equal to STATUS_BUFFER_TOO_SMALL, <b>WmiCompleteRequest</b> builds a WNODE_TOO_SMALL structure and returns STATUS_SUCCESS. The return value from <b>WmiCompleteRequest</b> should be returned by the driver in its <i>DpWmiXxx</i> routine.

## Remarks

A driver calls <b>WmiCompleteRequest</b> from a <i>DpWmiXxx</i> routine after it finishes all other processing in that routine, or after the driver finishes all processing for a pending IRP. <b>WmiCompleteRequest</b> fills in a <b>WNODE_<i>XXX</i></b> with any data returned by the driver and calls <b>IoCompleteRequest</b> to complete the IRP.

A driver should always return the return value from <b>WmiCompleteRequest</b> in its <i>DpWmiXxx</i> routine.

A driver must not call <b>WmiCompleteRequest</b> from its <a href="https://msdn.microsoft.com/library/windows/hardware/ff544097">DpWmiQueryRegInfo</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wmilib.h (include Wmilib.h) |
| **Library** | Wmilib.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544090">DpWmiExecuteMethod</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544094">DpWmiFunctionControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544096">DpWmiQueryDataBlock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544097">DpWmiQueryReginfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544104">DpWmiSetDataBlock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544108">DpWmiSetDataItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548343">IoCompleteRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565834">WmiSystemControl</a>