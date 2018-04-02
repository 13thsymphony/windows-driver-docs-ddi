---
UID: NC:ufxclient.EVT_UFX_DEVICE_TEST_MODE_SET
title: EVT_UFX_DEVICE_TEST_MODE_SET
author: windows-driver-content
description: The client driver's implementation to set the test mode of the function controller.
old-location: buses\evt_ufx_device_test_mode_set.htm
old-project: usbref
ms.assetid: 24B17B8E-C2F0-4CA8-AA9D-5EE86EB20CCC
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: EVT_UFX_DEVICE_TEST_MODE_SET, EvtUfxDeviceTestModeSet, EvtUfxDeviceTestModeSet callback function [Buses], PFN_UFX_DEVICE_TEST_MODE_SET, PFN_UFX_DEVICE_TEST_MODE_SET callback function pointer [Buses], buses.evt_ufx_device_test_mode_set, ufxclient/EvtUfxDeviceTestModeSet
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ufxclient.h
api_name:
-	PFN_UFX_DEVICE_TEST_MODE_SET
product:
- Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---


# EVT_UFX_DEVICE_TEST_MODE_SET callback function
The client driver's implementation to set the test mode of the function controller.

## Syntax

```
EVT_UFX_DEVICE_TEST_MODE_SET EvtUfxDeviceTestModeSet;

void EvtUfxDeviceTestModeSet(
  UFXDEVICE ,
  ULONG 
)
{...}
```

## Parameters

`Arg1`



`Arg1`




## Return Value

This callback function does not return a value.

## Remarks

The client driver for the function host controller registers its <i>EVT_UFX_DEVICE_TEST_MODE_SET</i> implementation with the USB function class extension (UFX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a> method.

The client driver indicates completion of this event by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a> method.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_UFX_DEVICE_TEST_MODE_SET UfxDevice_EvtDeviceTestModeSet;

VOID
UfxDevice_EvtDeviceTestModeSet (
    _In_ UFXDEVICE UfxDevice,
    _In_ ULONG TestMode
    )
/*++

Routine Description:

    EvtDeviceTestModeSet handler for the UFXDEVICE object.
    
    Handles a set test mode request from the host.  Places the controller into 
    the specified test mode.

Arguments:

    UfxDevice - UFXDEVICE object representing the device.

    TestMode - Test mode value.  See Section 7.1.20 of the USB 2.0 specification for definitions of 
               each test mode.

--*/
{
    NTSTATUS Status;

    UNREFERENCED_PARAMETER(TestMode);

    TraceEntry();

    //
    // #### TODO: Insert code to put the controller into the specified test mode ####
    //

    Status = STATUS_SUCCESS;

    UfxDeviceEventComplete(UfxDevice, Status);
    TraceExit();
}
</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ufxclient.h |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt187952">UfxDeviceEventComplete</a>