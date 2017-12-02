---
UID: NS.ufxbase._UFX_HARDWARE_FAILURE_CONTEXT
title: UFX_HARDWARE_FAILURE_CONTEXT
author: windows-driver-content
description: The UFX_HARDWARE_FAILURE_CONTEXT structure is used to define controller-specific hardware failure properties.
old-location: buses\ufx_hardware_failure_context.htm
old-project: usbref
ms.assetid: CA0268F3-44F0-4F64-A88D-9A2BBDE768EA
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: UFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ufxbase.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UFX_HARDWARE_FAILURE_CONTEXT
req.alt-loc: ufxbase.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
req.product: Windows 10 or later.
---

# UFX_HARDWARE_FAILURE_CONTEXT structure



## -description
<p>The <b>UFX_HARDWARE_FAILURE_CONTEXT</b> structure is used to define controller-specific hardware failure properties. </p>


## -syntax

````
typedef struct _UFX_HARDWARE_FAILURE_CONTEXT {
   Size;
   ExceptionCode;
   Data;
} UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT;
````


## -struct-fields
<dl>

### -field Size

<dd>
<p>The size of the <b>UFX_HARDWARE_FAILURE_CONTEXT</b> structure.</p>
</dd>

### -field ExceptionCode

<dd>
<p>The controller-specific hardware failure code.</p>
</dd>

### -field Data

<dd>
<p>A variable-length array of data associated with the hardware failure.</p>
</dd>
</dl>

## -remarks
<p>In cases where the function controller has experienced a fatal error, the client driver may allocate a variable-length <b>UFX_HARDWARE_FAILURE_CONTEXT</b> structure, set the <b>Size</b> field to the allocated size, set the <b>ExceptionCode</b> field to a value indicating the type of hardware error (as defined by the client driver) and fill in any associated information in the <b>Data</b> array.  It may then pass this structure to the <a href="..\ufxclient\nf-ufxclient-ufxdevicenotifyhardwarefailure.md">UfxDeviceNotifyHardwareFailure</a> UFX function. UFX will in turn pass this structure to the client driver’s <a href="..\ufxclient\nc-ufxclient-evt-ufx-device-controller-reset.md">EVT_UFX_DEVICE_CONTROLLER_RESET</a> event callback function (if it exists).</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ufxbase.h</dt>
</dl>
</td>
</tr>
</table>