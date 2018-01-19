---
UID : NF:ntddk.PsSetLoadImageNotifyRoutineEx
title : PsSetLoadImageNotifyRoutineEx function
author : windows-driver-content
description : The PsSetLoadImageNotifyRoutineEx routine registers a driver-supplied callback that is subsequently notified whenever an image is loaded (or mapped into memory).
old-location : kernel\pssetloadimagenotifyroutineex.htm
old-project : kernel
ms.assetid : 792cdb59-e0c2-4697-9934-b7e45a7a31a8
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : PsSetLoadImageNotifyRoutineEx
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10, version 1709
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : PsSetLoadImageNotifyRoutineEx
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe (kernel mode)
req.irql : PASSIVE_LEVEL
req.typenames : WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# PsSetLoadImageNotifyRoutineEx function
The <b>PsSetLoadImageNotifyRoutineEx</b> routine registers a driver-supplied callback that is subsequently notified whenever an image is loaded (or mapped into memory).

## Syntax

````
 NTSTATUS  PsSetLoadImageNotifyRoutineEx(
  _In_ PLOAD_IMAGE_NOTIFY_ROUTINE NotifyRoutine,
  _In_ ULONG_PTR                  Flags
);
````

## Parameters

`NotifyRoutine`

A pointer to the caller-implemented <a href="..\ntddk\nc-ntddk-pload_image_notify_routine.md">PLOAD_IMAGE_NOTIFY_ROUTINE</a> callback routine for load-image notifications.

`Flags`

Supplies a bitmask of flags that control the callback function. Here are the possible values:

<ul>
<li>PS_IMAGE_NOTIFY_CONFLICTING_ARCHITECTURE indicates that the callback routine should be invoked for all potentially executable images, including images that have a different architecture from the native architecture of the operating system.

</li>
</ul>


## Return Value

<dl>
<dt><b>STATUS_SUCCESS </b></dt>
</dl>The callback was successfully registered.
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>Invalid flag was supplied in <i>Flags</i>.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The routine failed allocate a callback block due to lack of resources.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |