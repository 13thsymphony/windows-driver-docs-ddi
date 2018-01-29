---
UID : NF:ufxclient.UfxDeviceIoInternalControl
title : UfxDeviceIoInternalControl function
author : windows-driver-content
description : Passes kernel mode IOCTLs to UFX.
old-location : buses\ufxdeviceiointernalcontrol.htm
old-project : usbref
ms.assetid : 0AD4316E-67E7-4810-86DA-5DEB5C4E6DE6
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : UfxDeviceIoInternalControl, buses.ufxdeviceiointernalcontrol, ufxclient/UfxDeviceIoInternalControl, UfxDeviceIoInternalControl method [Buses]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ufxclient.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PUFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT"
req.product : Windows 10 or later.
---


# UfxDeviceIoInternalControl function
Passes kernel mode IOCTLs to UFX.

## Syntax

````
BOOLEAN UfxDeviceIoInternalControl(
  [in] UFXDEVICE  UfxDevice,
  [in] WDFREQUEST Request,
  [in] size_t     OutputBufferLength,
  [in] size_t     InputBufferLength,
  [in] ULONG      IoControlCode
);
````

## Parameters

`UfxDevice`

A handle to a UFX device object that the driver created by calling <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.

`Request`

A handle to a framework request object.

`OutputBufferLength`

The length, in bytes, of the request's output buffer, if an output buffer is available.

`InputBufferLength`

The length, in bytes, of the request's input buffer, if an input buffer is available.

`IoControlCode`

The driver-defined or system-defined IOCTL that is associated with the request.


## Return Value

None

## Remarks

The client driver calls <b>UfxDeviceIoInternalControl</b> to forward internal IOCTLs that it receives in its <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_internal_device_control.md">EvtIoInternalDeviceControl</a> callback function to UFX.  The following example shows how:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
DefaultQueue_EvtIoInternalDeviceControl(
    _In_ WDFQUEUE Queue,
    _In_ WDFREQUEST Request,
    _In_ size_t OutputBufferLength,
    _In_ size_t InputBufferLength,
    _In_ ULONG IoControlCode
    )
/*++

Routine Description:

    EvtIoInternalDeviceControl handler for the default Queue

Arguments:

    Queue -  Handle to the framework queue object that is associated with the
             I/O request.

    Request - Handle to a framework request object.

    OutputBufferLength - Size of the output buffer in bytes

    InputBufferLength - Size of the input buffer in bytes

    IoControlCode - I/O control code.

--*/
{
    WDFDEVICE WdfDevice;
    PCONTROLLER_CONTEXT ControllerContext;
    BOOLEAN HandledbyUfx;   

    TraceEntry();

    TraceVerbose("InternalQueue 0x%p, Request 0x%p, OutputBufferLength %d, "
                  "InputBufferLength %d, IoControlCode %d",
                  Queue, Request, (int) OutputBufferLength, 
                  (int) InputBufferLength, IoControlCode);
    
    WdfDevice = WdfIoQueueGetDevice(Queue);
    ControllerContext = DeviceGetControllerContext(WdfDevice);

    HandledbyUfx = UfxDeviceIoInternalControl(
                        ControllerContext-&gt;UfxDevice,
                        Request,
                        OutputBufferLength,
                        InputBufferLength,
                        IoControlCode);

    if (!HandledbyUfx) {
        TraceError("Recieved an un supported IOCTL");
        WdfRequestComplete(Request, STATUS_INVALID_DEVICE_REQUEST);
    }

    TraceExit();
}
</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ufxclient.h |
| **Library** |  |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** |  |