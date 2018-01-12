---
UID: NF:strmini.StreamClassAbortOutstandingRequests
title: StreamClassAbortOutstandingRequests function
author: windows-driver-content
description: The StreamClassAbortOutstandingRequests routine aborts all outstanding requests, either to a particular stream, or to the entire driver.
old-location: stream\streamclassabortoutstandingrequests.htm
old-project: stream
ms.assetid: d60ef96b-d145-48e5-be56-7f0bc4d1d0f3
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: StreamClassAbortOutstandingRequests
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StreamClassAbortOutstandingRequests
req.alt-loc: Stream.lib,Stream.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Stream.lib
req.dll: 
req.irql: > DISPATCH_LEVEL
req.typenames: *PSTREAM_PRIORITY, STREAM_PRIORITY
req.product: Windows 10 or later.
---

# StreamClassAbortOutstandingRequests function



## -description
The <b>StreamClassAbortOutstandingRequests</b> routine aborts all outstanding requests, either to a particular stream, or to the entire driver.



## -syntax

````
VOID StreamClassAbortOutstandingRequests(
  _In_     PVOID             HwDeviceExtension,
  _In_opt_ PHW_STREAM_OBJECT HwStreamObject,
  _In_     NTSTATUS          Status
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the <a href="..\strmini\ns-strmini-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>. The class driver then passes pointers to the buffer in the <b>HwDeviceExtension</b> member of the <a href="..\strmini\ns-strmini-_hw_stream_request_block.md">HW_STREAM_REQUEST_BLOCK</a>, <a href="..\strmini\ns-strmini-_hw_stream_object.md">HW_STREAM_OBJECT</a>, <a href="..\strmini\ns-strmini-_hw_time_context.md">HW_TIME_CONTEXT</a>, and <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.


### -param HwStreamObject [in, optional]

Pointer to a <a href="..\strmini\ns-strmini-_hw_stream_object.md">HW_STREAM_OBJECT</a> that specifies which stream to abort requests on, or <b>NULL</b> to abort all requests to the minidriver. If this parameter is <b>NULL</b>, all device and stream requests are canceled.


### -param Status [in]

Specifies the status to be returned when an outstanding request is aborted. 


## -returns
None


## -remarks
This call also signals the class driver that the minidriver is ready to receive new requests of the type canceled.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Strmini.h (include Strmini.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Stream.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&gt; DISPATCH_LEVEL

</td>
</tr>
</table>