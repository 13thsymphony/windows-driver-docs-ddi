---
UID : NC:spbcx.EVT_SPB_CONTROLLER_WRITE
title : EVT_SPB_CONTROLLER_WRITE
author : windows-driver-content
description : An SPB controller driver's EvtSpbControllerIoWrite event callback function writes data to the specified target device from the buffers that are supplied with the write request.
old-location : spb\evtspbcontrolleriowrite.htm
old-project : SPB
ms.assetid : D97C3A17-309E-4364-8DFB-9073901D332E
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : SPB.evtspbcontrolleriowrite, EvtSpbControllerIoWrite callback function [Buses], EvtSpbControllerIoWrite, EVT_SPB_CONTROLLER_WRITE, EVT_SPB_CONTROLLER_WRITE, spbcx/EvtSpbControllerIoWrite
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : spbcx.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Supported starting with Windows 8.
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
req.lib : 
req.dll : 
req.irql : Called at IRQL <= DISPATCH_LEVEL.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSPB_TRANSFER_LIST_ENTRY, SPB_TRANSFER_LIST_ENTRY"
req.product : Windows 10 or later.
---


# EVT_SPB_CONTROLLER_WRITE function
An SPB controller driver's <i>EvtSpbControllerIoWrite</i> event callback function writes data to the specified target device from the buffers that are supplied with the write request.

## Syntax

```
EVT_SPB_CONTROLLER_WRITE EvtSpbControllerWrite;

void EvtSpbControllerWrite(
  WDFDEVICE Controller,
  SPBTARGET Target,
  SPBREQUEST Request,
  size_t Length
)
{...}
```

## Parameters

`Controller`

A WDFDEVICE handle to the <a href="https://msdn.microsoft.com/6be47eac-d6e4-43d1-bf2d-d49dcb2273c0">framework device object</a> that represents the SPB controller.

`Target`

An <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a> handle to the target for this I/O request. The target is a peripheral device or port that is attached to the bus. The SPB framework extension (SpbCx) previously assigned this handle to the target in the <a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a> callback that opened the connection to the target.

`Request`

An <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a> handle to the I/O request. Your SPB controller driver must complete this request either by performing the requested operation or by returning an error status. For more information, see Remarks.

`Length`

The number of bytes to write to the target device.


## Return Value

None.

## Remarks

SpbCx manages the I/O queue for the SPB controller. SpbCx calls the SPB controller driver's <i>EvtSpbControllerIoWrite</i> callback function when a client (peripheral driver) of the SPB controller sends an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a> request to a target device that is attached to the bus. The <i>Request</i> parameter value is a handle that encapsulates this request.

An <i>EvtSpbControllerIoWrite</i> callback does not return a status value. Instead, the SPB controller driver indicates the status of the write operation in the completion status for the I/O request.

An <i>EvtSpbControllerIoWrite</i> callback is asynchronous.  That is, the callback function should initiate the requested write operation and then return without waiting for the operation to complete. Later, the SPB controller driver completes the write request during an interrupt DPC or a timer DPC.

An <i>EvtSpbControllerIoWrite</i> callback does not return a status value. Instead, the SPB controller driver indicates the status of the write operation in the completion status for the I/O request.

If the write operation completes in full, the callback function should set the completion status to STATUS_SUCCESS. If the target device indicates that it cannot accept any more data before a transmission completes, the driver should set the completion status to STATUS_SUCCESS and specify the number of bytes transmitted.

If a transmission error occurs during the write operation, the driver should set the completion status in the I/O request to an appropriate error code. Not all buses provide a mechanism for a target device to report a transport error or a partially completed transfer, and not all controllers can detect these conditions.

To register an <i>EvtSpbControllerIoWrite</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a> method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | spbcx.h |
| **Library** |  |
| **IRQL** | Called at IRQL <= DISPATCH_LEVEL. |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/2BC0E6E7-7EE1-487A-9276-AE8EBB3FFD43">EvtSpbControllerIoRead</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a>

<a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450919">SpbDeviceInitialize</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20EVT_SPB_CONTROLLER_WRITE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>