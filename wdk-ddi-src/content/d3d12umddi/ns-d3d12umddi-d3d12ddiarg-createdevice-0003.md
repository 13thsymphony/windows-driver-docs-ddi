---
UID: NS.d3d12umddi.D3D12DDIARG_CREATEDEVICE_0003
title: D3D12DDIARG_CREATEDEVICE_0003
author: windows-driver-content
description: The D3D10DDIARG_CREATEDEVICE_0003 structure describes the display device to create.
old-location: display\d3d12ddiarg_createdevice_0003.htm
old-project: display
ms.assetid: F139A61B-E074-4185-A934-17F6FDBA3F62
ms.author: windowsdriverdev
ms.date: 11/14/2017
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
req.iface: 
---

# D3D12DDIARG_CREATEDEVICE_0003 structure



## -description
<p>The D3D10DDIARG_CREATEDEVICE_0003 structure describes the display device to create.</p>


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
<dl>

### -field <b>hRTDevice</b>

<dd>
<p>[in] A handle to the display device (graphics context) that specifies the handle that the driver should use when it calls back into the Direct3D runtime. </p>
</dd>

### -field <b>Interface</b>

<dd>
<p>[in] The Direct3D interface version.</p>
</dd>

### -field <b>Version</b>

<dd>
<p>[in] A UINT value that the driver can use to identify when the Direct3D runtime was built.</p>
</dd>

### -field <b>pKTCallbacks</b>

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544512">D3DDDI_DEVICECALLBACKS</a> structure that contains a table of Direct3D runtime callback functions that the driver can use to access kernel services.</p>
</dd>

### -field <b>hDrvDevice</b>

<dd>
<p> A handle to the display device (graphics context) that the Direct3D runtime uses in subsequent driver calls to identify the display device.</p>
</dd>

### -field <b>p12UMCallbacks</b>

<dd>
<p> A pointer to a D3D12DDI_CORELAYER_DEVICECALLBACKS_0003 structure that contains a table of Direct3D runtime callback functions that the driver can use to access core user-mode runtime functionality. </p>
</dd>

### -field <b>p12UMCallbacks_0022</b>

<dd>
<p>A pointer to a D3D12DDI_CORELAYER_DEVICECALLBACKS_0022 structure that contains a table of Direct3D runtime callback functions that the driver can use to access core user-mode runtime functionality. </p>
</dd>

### -field <b>Flags</b>

<dd>
<p>Flag values that identify how to create the display device.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h</dt>
</dl>
</td>
</tr>
</table>