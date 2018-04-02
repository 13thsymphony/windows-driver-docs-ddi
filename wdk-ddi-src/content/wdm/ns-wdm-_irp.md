---
UID: NS:wdm._IRP
title: "_IRP"
author: windows-driver-content
description: The IRP structure is a partially opaque structure that represents an I/O request packet. Drivers can use the following members of the IRP structure.
old-location: kernel\irp.htm
old-project: kernel
ms.assetid: 6e044704-2edf-416f-a5a1-2ae65363a165
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PIRP, IRP, IRP structure [Kernel-Mode Driver Architecture], PIRP, PIRP structure pointer [Kernel-Mode Driver Architecture], _IRP, kernel.irp, kstruct_b_39688b8b-4b33-4bce-b71f-e9c183e4d6bd.xml, wdm/IRP, wdm/PIRP"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	IRP
product: Windows
targetos: Windows
req.typenames: IRP
req.product: Windows 10 or later.
---

# _IRP structure
The <b>IRP</b> structure is a partially opaque structure that represents an <i>I/O request packet</i>. Drivers can use the following members of the IRP structure.

## Syntax
```
typedef struct _IRP {
  CSHORT                    Type;
  USHORT                    Size;
  PMDL                      MdlAddress;
  ULONG                     Flags;
  union {
    __volatile LONG IrpCount;
    _IRP            *MasterIrp;
    PVOID           SystemBuffer;
  } AssociatedIrp;
  LIST_ENTRY                ThreadListEntry;
  IO_STATUS_BLOCK           IoStatus;
  KPROCESSOR_MODE           RequestorMode;
  BOOLEAN                   PendingReturned;
  CHAR                      StackCount;
  CHAR                      CurrentLocation;
  BOOLEAN                   Cancel;
  KIRQL                     CancelIrql;
  CCHAR                     ApcEnvironment;
  UCHAR                     AllocationFlags;
  PIO_STATUS_BLOCK          UserIosb;
  PKEVENT                   UserEvent;
  union {
    LARGE_INTEGER AllocationSize;
    struct {
      union {
        PVOID           IssuingProcess;
        PIO_APC_ROUTINE UserApcRoutine;
      };
      PVOID UserApcContext;
    } AsynchronousParameters;
  } Overlay;
  __volatile PDRIVER_CANCEL CancelRoutine;
  PVOID                     UserBuffer;
  union {
    KAPC  Apc;
    PVOID CompletionKey;
    struct {
      union {
        KDEVICE_QUEUE_ENTRY DeviceQueueEntry;
        struct {
          PVOID DriverContext[4];
        };
      };
      PETHREAD     Thread;
      PCHAR        AuxiliaryBuffer;
      struct {
        LIST_ENTRY ListEntry;
        struct {
          _IO_STACK_LOCATION *CurrentStackLocation;
          struct             _IO_STACK_LOCATION;
          ULONG              PacketType;
        };
      };
      PFILE_OBJECT OriginalFileObject;
    } Overlay;
  } Tail;
} IRP;
```

## Members


`Type`



`Size`



`MdlAddress`

Pointer to an MDL describing a user buffer, if the driver is using direct I/O, and the IRP major function code is one of the following:





#### IRP_MJ_READ

The MDL describes an empty buffer that the device or driver fills in.



#### IRP_MJ_WRITE

The MDL describes a buffer that contains data for the device or driver.



#### IRP_MJ_DEVICE_CONTROL or IRP_MJ_INTERNAL_DEVICE_CONTROL

If the IOCTL code specifies the METHOD_IN_DIRECT transfer type, the MDL describes a buffer that contains data for the device or driver.

If the IOCTL code specifies the METHOD_OUT_DIRECT transfer type, the MDL describes an empty buffer that the device or driver fills in.

For more information about the buffers that are associated with METHOD_IN_DIRECT and METHOD_OUT_DIRECT transfer types in IOCTL codes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540663">Buffer Descriptions for I/O Control Codes</a>.

If the driver is not using direct I/O, this pointer is <b>NULL</b>.

`Flags`

File system drivers use this field, which is read-only for all drivers. Network and, possibly, highest-level device drivers also might read this field. This field is set either to zero or to the bitwise-OR of one or more of the following system-defined flag bits:

IRP_NOCACHE

IRP_PAGING_IO

IRP_MOUNT_COMPLETION

IRP_SYNCHRONOUS_API

IRP_ASSOCIATED_IRP

IRP_BUFFERED_IO

IRP_DEALLOCATE_BUFFER

IRP_INPUT_OPERATION

IRP_SYNCHRONOUS_PAGING_IO

IRP_CREATE_OPERATION

IRP_READ_OPERATION

IRP_WRITE_OPERATION

IRP_CLOSE_OPERATION

IRP_DEFER_IO_COMPLETION

IRP_OB_QUERY_NAME

IRP_HOLD_DEVICE_QUEUE

IRP_UM_DRIVER_INITIATED_IO

`AssociatedIrp`

#### MasterIrp

Pointer to the master IRP in an IRP that was created by a highest-level driver's call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff549397">IoMakeAssociatedIrp</a>.



#### SystemBuffer

Pointer to a system-space buffer.

If the driver is using buffered I/O, the buffer's purpose is determined by the IRP major function code, as follows:





##### IRP_MJ_READ

The buffer receives data from the device or driver. The buffer's length is specified by <b>Parameters.Read.Length</b> in the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a> structure.

<b>NULL</b>.



##### IRP_MJ_WRITE

The buffer supplies data for the device or driver. The buffer's length is specified by <b>Parameters.Write.Length</b> in the driver's <b>IO_STACK_LOCATION</b> structure.

<b>NULL</b>.



##### IRP_MJ_DEVICE_CONTROL or IRP_MJ_INTERNAL_DEVICE_CONTROL

The buffer represents both the input and output buffers that are supplied to <b>DeviceIoControl</b> and <b>IoBuildDeviceIoControlRequest</b>. Output data overwrites input data.

For input, the buffer's length is specified by <b>Parameters.DeviceIoControl.InputBufferLength</b> in the driver's <b>IO_STACK_LOCATION</b> structure.

For output, the buffer's length is specified by <b>Parameters.DeviceIoControl.OutputBufferLength</b> in the driver's <b>IO_STACK_LOCATION</b> structure.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540663">Buffer Descriptions for I/O Control Codes</a>.

The buffer represents the input buffer that is supplied to <b>DeviceIoControl</b> and <b>IoBuildDeviceIoControlRequest</b>.

The buffer's length is specified by <b>Parameters.DeviceIoControl.InputBufferLength</b> in the driver's <b>IO_STACK_LOCATION</b> structure.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540663">Buffer Descriptions for I/O Control Codes</a>.

If the driver is using direct I/O, the buffer's purpose is determined by the IRP major function code, as follows:

`ThreadListEntry`



`IoStatus`

Contains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a> structure in which a driver stores status and information before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548343">IoCompleteRequest</a>.

`RequestorMode`

Indicates the execution mode of the original requester of the operation, one of <b>UserMode</b> or <b>KernelMode</b>.

`PendingReturned`

If set to <b>TRUE</b>, a driver has marked the IRP pending. Each <a href="https://msdn.microsoft.com/library/windows/hardware/ff548354">IoCompletion</a> routine should check the value of this flag. If the flag is <b>TRUE</b>, and if the IoCompletion routine will not return STATUS_MORE_PROCESSING_REQUIRED, the routine should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549422">IoMarkIrpPending</a> to propagate the pending status to drivers above it in the device stack.

`StackCount`



`CurrentLocation`



`Cancel`

If set to <b>TRUE</b>, the IRP either is or should be canceled.

`CancelIrql`

Contains the IRQL at which a driver is running when <a href="https://msdn.microsoft.com/library/windows/hardware/ff548196">IoAcquireCancelSpinLock</a> is called.

`ApcEnvironment`



`AllocationFlags`



`UserIosb`



`UserEvent`



`Overlay`



`CancelRoutine`

Contains the entry point for a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/hh406716">Cancel</a> routine to be called if the IRP is canceled. <b>NULL</b> indicates that the IRP is not currently cancelable.

`UserBuffer`

Contains the address of an output buffer if both of the following conditions apply:

<ul>
<li>The major function code in the I/O stack location is <a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>.</li>
<li>The I/O control code was defined with METHOD_NEITHER or METHOD_BUFFERED.</li>
</ul>
For METHOD_BUFFERED, the driver should use the buffer pointed to by <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> as the output buffer. When the driver completes the request, the I/O manager copies the contents of this buffer to the output buffer that is pointed to by <b>Irp-&gt;UserBuffer</b>. The driver should not write directly to the buffer pointed to by <b>Irp-&gt;UserBuffer</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540663">Buffer Descriptions for I/O Control Codes</a>.

`Tail`



## Remarks
Undocumented members of the IRP structure are reserved, used only by the I/O manager or, in some cases, by FSDs.

An IRP is the basic I/O manager structure used to communicate with drivers and to allow drivers to communicate with each other. A packet consists of two different parts:

<ul>
<li>
<i>Header</i>, or <i>fixed part of the packet</i>— This is used by the I/O manager to store information about the original request, such as the caller's device-independent parameters, the address of the device object upon which a file is open, and so on. It is also used by drivers to store information such as the final status of the request.

</li>
<li>
<i>I/O stack locations</i>— Following the header is a set of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551821">I/O stack locations</a>, one per driver in the chain of layered drivers for which the request is bound. Each stack location contains the parameters, function codes, and context used by the corresponding driver to determine what it is supposed to be doing. For more information, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a> structure.

</li>
</ul>
While a higher-level driver might check the value of the <b>Cancel</b> Boolean in an IRP, that driver cannot assume the IRP will be completed with STATUS_CANCELLED by a lower-level driver even if the value is <b>TRUE</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550659">IO_STACK_LOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550671">IO_STATUS_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548397">IoCreateDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549174">IoGetCurrentIrpStackLocation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549266">IoGetNextIrpStackLocation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549674">IoSetCancelRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550321">IoSetNextIrpStackLocation</a>