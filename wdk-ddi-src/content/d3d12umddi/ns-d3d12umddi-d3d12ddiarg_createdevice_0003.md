---
UID: NS.D3D12UMDDI.D3D12DDIARG_CREATEDEVICE_0003
title: D3D12DDIARG_CREATEDEVICE_0003
author: windows-driver-content
description: The D3D10DDIARG_CREATEDEVICE_0003 structure describes the display device to create.
old-location: display\d3d12ddiarg_createdevice_0003.htm
old-project: display
ms.assetid: F139A61B-E074-4185-A934-17F6FDBA3F62
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D12DDIARG_CREATEDEVICE_0003, D3D12DDIARG_CREATEDEVICE_0003
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDIARG_CREATEDEVICE_0003
req.alt-loc: d3d12umddi.h
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
---

# D3D12DDIARG_CREATEDEVICE_0003 structure



## -description
The D3D10DDIARG_CREATEDEVICE_0003 structure describes the display device to create.



## -syntax

````
typedef struct _D3D12DDIARG_CREATEDEVICE_0003 {
  D3D12DDI_HRTDEVICE           hRTDevice;
  UINT                         Interface;
  UINT                         Version;
  const D3DDDI_DEVICECALLBACKS *pKTCallbacks;
  D3D12DDI_HDEVICE             hDrvDevice;
  union {
    const D3D12DDI_CORELAYER_DEVICECALLBACKS_0003 *p12UMCallbacks;
    const D3D12DDI_CORELAYER_DEVICECALLBACKS_0022 *p12UMCallbacks_0022;
  };
  D3D12DDI_CREATE_DEVICE_FLAGS Flags;
} D3D12DDIARG_CREATEDEVICE_0003;
````


## -struct-fields

### -field hRTDevice

[in] A handle to the display device (graphics context) that specifies the handle that the driver should use when it calls back into the Direct3D runtime. 


### -field Interface

[in] The Direct3D interface version.


### -field Version

[in] A UINT value that the driver can use to identify when the Direct3D runtime was built.


### -field pKTCallbacks

A pointer to a <a href="display.d3dddi_devicecallbacks">D3DDDI_DEVICECALLBACKS</a> structure that contains a table of Direct3D runtime callback functions that the driver can use to access kernel services.


### -field hDrvDevice

 A handle to the display device (graphics context) that the Direct3D runtime uses in subsequent driver calls to identify the display device.


### -field p12UMCallbacks

 A pointer to a D3D12DDI_CORELAYER_DEVICECALLBACKS_0003 structure that contains a table of Direct3D runtime callback functions that the driver can use to access core user-mode runtime functionality. 


### -field p12UMCallbacks_0022

A pointer to a D3D12DDI_CORELAYER_DEVICECALLBACKS_0022 structure that contains a table of Direct3D runtime callback functions that the driver can use to access core user-mode runtime functionality. 


### -field Flags

Flag values that identify how to create the display device.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h</dt>
</dl>
</td>
</tr>
</table>