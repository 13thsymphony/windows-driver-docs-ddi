---
UID: NS.UFXBASE._UFX_HARDWARE_FAILURE_CONTEXT
title: _UFX_HARDWARE_FAILURE_CONTEXT
author: windows-driver-content
description: The UFX_HARDWARE_FAILURE_CONTEXT structure is used to define controller-specific hardware failure properties.
old-location: buses\ufx_hardware_failure_context.htm
old-project: UsbRef
ms.assetid: CA0268F3-44F0-4F64-A88D-9A2BBDE768EA
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _UFX_HARDWARE_FAILURE_CONTEXT, PUFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT, UFX_HARDWARE_FAILURE_CONTEXT
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
req.product: Windows 10 or later.
---

# _UFX_HARDWARE_FAILURE_CONTEXT structure



## -description
The <b>UFX_HARDWARE_FAILURE_CONTEXT</b> structure is used to define controller-specific hardware failure properties. 



## -syntax

````
typedef struct _UFX_HARDWARE_FAILURE_CONTEXT {
   Size;
   ExceptionCode;
   Data;
} UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT;
````


## -struct-fields

### -field Size

The size of the <b>UFX_HARDWARE_FAILURE_CONTEXT</b> structure.


### -field ExceptionCode

The controller-specific hardware failure code.


### -field Data

A variable-length array of data associated with the hardware failure.


## -remarks
In cases where the function controller has experienced a fatal error, the client driver may allocate a variable-length <b>UFX_HARDWARE_FAILURE_CONTEXT</b> structure, set the <b>Size</b> field to the allocated size, set the <b>ExceptionCode</b> field to a value indicating the type of hardware error (as defined by the client driver) and fill in any associated information in the <b>Data</b> array.  It may then pass this structure to the <a href="buses.ufxdevicenotifyhardwarefailure">UfxDeviceNotifyHardwareFailure</a> UFX function. UFX will in turn pass this structure to the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_controller_reset.md">EVT_UFX_DEVICE_CONTROLLER_RESET</a> event callback function (if it exists).


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ufxbase.h</dt>
</dl>
</td>
</tr>
</table>