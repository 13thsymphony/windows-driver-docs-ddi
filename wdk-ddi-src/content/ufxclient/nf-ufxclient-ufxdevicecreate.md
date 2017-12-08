---
UID: NF.ufxclient.UfxDeviceCreate
title: UfxDeviceCreate function
author: windows-driver-content
description: Creates a UFX device object, registers event callback routines, and specifies capabilities specific to the controller.
old-location: buses\ufxdevicecreate.htm
old-project: usbref
ms.assetid: BA86280E-8324-4D98-B16C-504D427A6A4B
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: UfxDeviceCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UfxDeviceCreate
req.alt-loc: ufxclient.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# UfxDeviceCreate function



## -description
Creates a UFX device object, registers event callback routines, and specifies capabilities specific to the controller.


## -syntax

````
NTSTATUS UfxDeviceCreate(
  [in]           WDFDEVICE                Device,
  [in]           UFX_DEVICE_CALLBACKS     Callbacks,
  [in]           PUFX_DEVICE_CAPABILITIES Capabilities,
  [in, optional] PWDF_OBJECT_ATTRIBUTES   Attributes,
  [out]          UFXDEVICE                *UfxDevice
);
````


## -parameters

### -param Device [in]

A handle to a WDF device object.

### -param Callbacks [in]

A structure of type <a href="buses.ufx_device_callbacks">UFX_DEVICE_CALLBACKS</a> that contains pointers to driver-supplied callback routines to be associated with the UFX device object.

### -param Capabilities [in]

A pointer to a <a href="buses.ufx_device_capabilities">UFX_DEVICE_CAPABILITIES</a> structure.

### -param Attributes [in, optional]

A pointer to a <a href="wdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains driver-supplied attributes for the new object. This parameter is optional and can be <b>WDF_NO_OBJECT_ATTRIBUTES</b>.

### -param UfxDevice [out]

A pointer to a location that receives a handle to the new UFX device object.



## -returns
If the operation is successful, the method returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE.

## -remarks
The client driver must call <a href="wdf.wdfdevicecreate">WdfDeviceCreate</a> before it calls <b>UfxDeviceCreate</b>. Typically, the client driver calls  <b>UfxDeviceCreate</b> from its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback routine.

The following code snippet shows how to call <b>UfxDeviceCreate</b>.

## -requirements
<table>
<tr>
<th width="30%">
Minimum support
</th>
<td width="70%">
Windows 10
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ufxclient.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>