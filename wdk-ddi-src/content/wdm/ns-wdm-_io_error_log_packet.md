---
UID: NS:wdm._IO_ERROR_LOG_PACKET
title: "_IO_ERROR_LOG_PACKET"
author: windows-driver-content
description: The IO_ERROR_LOG_PACKET structure serves as the header for an error log entry.
old-location: kernel\io_error_log_packet.htm
old-project: kernel
ms.assetid: 4bf54017-d142-4534-8a5a-c7f267a1554b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/IO_ERROR_LOG_PACKET, PIO_ERROR_LOG_PACKET structure pointer [Kernel-Mode Driver Architecture], *PIO_ERROR_LOG_PACKET, kernel.io_error_log_packet, IO_ERROR_LOG_PACKET structure [Kernel-Mode Driver Architecture], _IO_ERROR_LOG_PACKET, PIO_ERROR_LOG_PACKET, kstruct_b_04c24dbc-a479-437c-adc2-b29294596564.xml, wdm/PIO_ERROR_LOG_PACKET, IO_ERROR_LOG_PACKET
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	IO_ERROR_LOG_PACKET
product: Windows
targetos: Windows
req.typenames: "*PIO_ERROR_LOG_PACKET, IO_ERROR_LOG_PACKET"
req.product: Windows 10 or later.
---

# _IO_ERROR_LOG_PACKET structure
The <b>IO_ERROR_LOG_PACKET</b> structure serves as the header for an error log entry.

## Syntax
````
typedef struct _IO_ERROR_LOG_PACKET {
  UCHAR         MajorFunctionCode;
  UCHAR         RetryCount;
  USHORT        DumpDataSize;
  USHORT        NumberOfStrings;
  USHORT        StringOffset;
  USHORT        EventCategory;
  NTSTATUS      ErrorCode;
  ULONG         UniqueErrorValue;
  NTSTATUS      FinalStatus;
  ULONG         SequenceNumber;
  ULONG         IoControlCode;
  LARGE_INTEGER DeviceOffset;
  ULONG         DumpData[1];
} IO_ERROR_LOG_PACKET, *PIO_ERROR_LOG_PACKET;
````

## Members


`DeviceOffset`

Specifies the driver-specified offset into the device where the error occurred. Setting this value is optional.

`DumpData`

A variable-size array that can be used to store driver-specific binary data, such as register values or any other information useful in identifying the cause of the error. Drivers must specify the size, in bytes, of the array in the <b>DumpDataSize</b> member of this structure.

`DumpDataSize`

Indicates the size, in bytes, of the variable-length <b>DumpData</b> member of this structure. The specified value must be a multiple of <b>sizeof</b>(ULONG).

`ErrorCode`

Specifies the type of error. The Event Viewer uses the error code to determine which string to display as the Description value for the error. The Event Viewer takes the string template for the error supplied in the driver's message catalog, replaces "%1" in the template with the name of the driver's device object, and replaces "%2" through "%<i>n</i>" with the insertion strings supplied with the error log entry.

<b>ErrorCode</b> is a system-defined or driver-defined constant; see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554312">Logging Errors</a> for more information.

`EventCategory`

Specifies the event category for the error. A driver specifies the event categories it supports and corresponding descriptive strings in its message catalog. The Event Viewer displays the descriptive string as the <b>Category</b> value for the error.

`FinalStatus`

Specifies the NTSTATUS value to be returned for the operation that triggered the error. Setting this value is optional.

`IoControlCode`

For an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a> IRP, this member specifies the I/O control code for the request that trigged the error. Otherwise, this value is zero. Setting this value is optional.

`MajorFunctionCode`

Indicates the <b>IRP_MJ_<i>XXX</i></b> major function code of the IRP the driver was handling when the error occurred. Setting this value is optional.

`NumberOfStrings`

Indicates the number of insertion strings the driver will supply with this error log entry. Drivers set this value to zero for errors that need no insertion strings. The Event Viewer uses these strings to fill in the "%2" through "%<i>n</i>" entries in the string template for this error code.

The null-terminated Unicode strings themselves follow the <b>IO_ERROR_LOG_PACKET</b> structure in memory.

`RetryCount`

Indicates the number of times the driver has retried the operation and encountered this error. Use zero to indicate the driver attempted the operation once, or add one for each retry beyond the initial attempt.

`SequenceNumber`

Specifies a driver-assigned sequence number for the current IRP, which should be constant for the life of a given request. Setting this value is optional.

`StringOffset`

Indicates the offset, in bytes, from the beginning of the structure, at which any driver-supplied insertion string data begins. Normally this will be <b>sizeof</b>(<b>IO_ERROR_LOG_PACKET</b>) plus the value of the <b>DumpDataSize</b> member. If there are no driver-supplied insertion strings, <b>StringOffset</b> can be zero.

`UniqueErrorValue`

A driver-specific value that indicates where the error was detected in the driver. Setting this value is optional.

## Remarks
Drivers use the <a href="..\wdm\nf-wdm-ioallocateerrorlogentry.md">IoAllocateErrorLogEntry</a> routine to allocate an error log entry. The <b>IO_ERROR_LOG_PACKET</b> structure serves as the header for the returned buffer. It is followed in memory by any insertion strings for the log entry.

Note that the I/O manager itself inserts some information into the system error log, such as the name of the device and driver. The I/O manager reserves 80 bytes to hold this information. If the size of this information exceeds 80 bytes, then the I/O manager truncates the driver's insertion strings as necessary.

For more information about how to use this structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554312">Logging Errors</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>

<a href="..\ntifs\nf-ntifs-iowriteerrorlogentry.md">IoWriteErrorLogEntry</a>

<a href="..\wdm\nf-wdm-ioallocateerrorlogentry.md">IoAllocateErrorLogEntry</a>

<a href="..\wdm\nf-wdm-iofreeerrorlogentry.md">IoFreeErrorLogEntry</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IO_ERROR_LOG_PACKET structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>