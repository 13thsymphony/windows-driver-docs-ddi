---
UID: NS:d3d12umddi.D3D12DDIARG_CREATEDEVICE_0003
title: D3D12DDIARG_CREATEDEVICE_0003
author: windows-driver-content
description: The D3D10DDIARG_CREATEDEVICE_0003 structure describes the display device to create.
old-location: display\d3d12ddiarg_createdevice_0003.htm
old-project: display
ms.assetid: F139A61B-E074-4185-A934-17F6FDBA3F62
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDIARG_CREATEDEVICE_0003, D3D12DDIARG_CREATEDEVICE_0003 structure [Display Devices], d3d12umddi/D3D12DDIARG_CREATEDEVICE_0003, display.d3d12ddiarg_createdevice_0003
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDIARG_CREATEDEVICE_0003
product: Windows
targetos: Windows
req.typenames: D3D12DDIARG_CREATEDEVICE_0003
---

# D3D12DDIARG_CREATEDEVICE_0003 structure
The D3D10DDIARG_CREATEDEVICE_0003 structure describes the display device to create.

## Syntax
```
typedef struct D3D12DDIARG_CREATEDEVICE_0003 {
  D3D12DDI_HRTDEVICE           hRTDevice;
  UINT                         Interface;
  UINT                         Version;
  CONST D3DDDI_DEVICECALLBACKS *pKTCallbacks;
  D3D12DDI_HDEVICE             hDrvDevice;
  union {
    CONST D3D12DDI_CORELAYER_DEVICECALLBACKS_0003 *p12UMCallbacks;
    CONST D3D12DDI_CORELAYER_DEVICECALLBACKS_0022 *p12UMCallbacks_0022;
  };
  D3D12DDI_CREATE_DEVICE_FLAGS Flags;
};
```

## Members


`hRTDevice`

[in] A handle to the display device (graphics context) that specifies the handle that the driver should use when it calls back into the Direct3D runtime.

`Interface`

[in] The Direct3D interface version.

`Version`

[in] A UINT value that the driver can use to identify when the Direct3D runtime was built.

`pKTCallbacks`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a> structure that contains a table of Direct3D runtime callback functions that the driver can use to access kernel services.

`hDrvDevice`

A handle to the display device (graphics context) that the Direct3D runtime uses in subsequent driver calls to identify the display device.

`Flags`

Flag values that identify how to create the display device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h |