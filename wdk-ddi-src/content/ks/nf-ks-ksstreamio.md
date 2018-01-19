---
UID : NF:ks.KsStreamIo
title : KsStreamIo function
author : windows-driver-content
description : The KsStreamIo function performs a stream read or write against the specified file object. The function attempts to use FastIoDispatch if possible, or it generates a read or write request against the device object.
old-location : stream\ksstreamio.htm
old-project : stream
ms.assetid : 74c62a30-42b9-4ea7-b52a-014e263d886e
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsStreamIo
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KsStreamIo
req.alt-loc : Ks.lib,Ks.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ks.lib
req.dll : 
req.irql : 
req.typenames : 
---


# KsStreamIo function
The <b>KsStreamIo</b> function performs a stream read or write against the specified file object. The function attempts to use <b>FastIoDispatch</b> if possible, or it generates a read or write request against the device object.

## Syntax

````
NTSTATUS KsStreamIo(
  _In_     PFILE_OBJECT            FileObject ,
  _In_opt_ PKEVENT                 Event ,
  _In_opt_ PVOID                   PortContext ,
  _In_opt_ PIO_COMPLETION_ROUTINE  CompletionRoutine ,
  _In_opt_ PVOID                   CompletionContext ,
  _In_opt_ KSCOMPLETION_INVOCATION CompletionInvocationFlags ,
  _Out_    PIO_STATUS_BLOCK        IoStatusBlock ,
  _Inout_  PVOID                   StreamHeaders ,
  _In_     ULONG                   Length ,
  _In_     ULONG                   Flags ,
  _In_     KPROCESSOR_MODE         RequestorMode 
);
````

## Parameters

`FileObject`

Specifies the file object to perform the I/O against.

`Event`

Optionally contains the event to use in the I/O. If none is passed, the call is assumed to be on a synchronous file object or the caller is waiting for the file object's event, or else it can be asynchronously completed. If used, and the KSSTREAM_SYNCHRONOUS flag is not set, this must be an event allocated by the object manager. If the caller is performing asynchronous I/O, it must either wait for the file object's event or pass an event in this parameter and wait for it. If this is not done, then there is no way for the caller to know when the IoStatusBlock has been updated by the call.

`PortContext`

Optionally contains context information for a completion port.

`CompletionRoutine`

Optionally points to a completion routine for this IRP.

`CompletionContext`

If <i>CompletionRoutine</i> is specified, this provides a context pointer in the completion routine callback.

`OPTIONAL`



`IoStatusBlock`

Location to return the status information. This is always assumed to be a valid address, regardless of the requester mode. The value must remain valid until the call has updated the status. The caller must either perform synchronous I/O or must wait for the file object's event or an event passed in the Event parameter before allowing this address to become invalid.

`StreamHeaders`

Specifies the list of stream headers. This address, as well as the addresses of the data buffers, are assumed to have been probed for appropriate access. Kernel-mode clients submitting streaming headers must allocate the headers from NonPagedPool memory.

`Length`

Specifies the size of the <i>StreamHeaders</i> passed.

`Flags`

Specifies various flags for the I/O. See the following table for the values used.

`RequestorMode`

Indicates the processor mode to place in the IRP if one is needs to be generated. This variable also determines if a fast I/O call can be performed. If the requester mode is not kernel mode, but the previous mode is, then fast I/O cannot be used.


## Return Value

The <b>KsStreamIo</b> function returns STATUS_SUCCESS if successful, STATUS_PENDING if action is pending, or if unsuccessful it returns an I/O error.

## Remarks

The following enumerated values are used for the <i>CompletionInvocationFlags</i> variable and are of type KSCOMPLETION_INVOCATION:

KsInvokeOnSuccess

Invokes the completion routine on success.

KsInvokeOnError

Invokes the completion routine on error.

KsInvokeOnCancel

Invokes the completion routine on cancellation.

The following defined values are used for the <i>Flags</i> variable:

KSSTREAM_READ

Specifies that an IOCTL_KS_STREAMREAD IRP is to be built. This is the default.

KSSTREAM_WRITE

Specifies that an IOCTL_KS_STREAMWRITE IRP is to be built.

KSSTREAM_PAGED_DATA

Specifies that the data is pageable. This is the default and can be used at all times.

KSSTREAM_NONPAGED_DATA

Specifies that the data is nonpaged and can be used as a performance enhancement.

KSSTREAM_SYNCHRONOUS

Specifies that the IRP is synchronous. This means that if the <i>Event</i> parameter is passed, it is not treated as an object manager event and is not referenced or dereferenced.

KSSTREAM_READ is equivalent to KSPROBE_STREAMREAD.

Similarly, KSSTREAM_WRITE is equivalent to KSPROBE_STREAMWRITE.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |