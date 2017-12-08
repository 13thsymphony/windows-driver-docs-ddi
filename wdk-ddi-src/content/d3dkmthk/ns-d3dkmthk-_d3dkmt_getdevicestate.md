---
UID: NS.D3DKMTHK._D3DKMT_GETDEVICESTATE
title: _D3DKMT_GETDEVICESTATE
author: windows-driver-content
description: The D3DKMT_GETDEVICESTATE structure describes parameters for retrieving the state of a device.
old-location: display\d3dkmt_getdevicestate.htm
old-project: display
ms.assetid: b90f8b63-51d3-4de4-9d8b-91926150fd30
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DKMT_GETDEVICESTATE, D3DKMT_GETDEVICESTATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_GETDEVICESTATE
req.alt-loc: d3dkmthk.h
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

# _D3DKMT_GETDEVICESTATE structure



## -description
The D3DKMT_GETDEVICESTATE structure describes parameters for retrieving the state of a device. 


## -syntax

````
typedef struct _D3DKMT_GETDEVICESTATE {
  D3DKMT_HANDLE           hDevice;
  D3DKMT_DEVICESTATE_TYPE StateType;
  union {
    D3DKMT_DEVICEEXECUTION_STATE ExecutionState;
    D3DKMT_DEVICEPRESENT_STATE   PresentState;
    D3DKMT_DEVICERESET_STATE     ResetState;
  };
} D3DKMT_GETDEVICESTATE;
````


## -struct-fields

### -field hDevice

[in] A handle to the device that status is requested for.

### -field StateType

[in] A <a href="display.d3dkmt_devicestate_type">D3DKMT_DEVICESTATE_TYPE</a>-typed value that indicates the type of status to retrieve for the device.

### -field ExecutionState

[out] A <a href="display.d3dkmt_deviceexecution_state">D3DKMT_DEVICEEXECUTION_STATE</a>-typed value that indicates the execution status of the device. The union that is contained in D3DKMT_GETDEVICESTATE holds a value from this enumeration if the <b>StateType</b> member is D3DKMT_DEVICESTATE_EXECUTION. 

### -field PresentState

[in/out] A <a href="display.d3dkmt_devicepresent_state">D3DKMT_DEVICEPRESENT_STATE</a> structure that describes parameters for retrieving the present status of the device. The union that is contained in D3DKMT_GETDEVICESTATE holds a structure of this type if the <b>StateType</b> member is D3DKMT_DEVICESTATE_PRESENT. 

### -field ResetState

[out] A <a href="display.d3dkmt_devicereset_state">D3DKMT_DEVICERESET_STATE</a> structure that describes the reset status of the device. The union that is contained in D3DKMT_GETDEVICESTATE holds a structure of this type if the <b>StateType</b> member is D3DKMT_DEVICESTATE_RESET. 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dkmt_deviceexecution_state">D3DKMT_DEVICEEXECUTION_STATE</a>
</dt>
<dt>
<a href="display.d3dkmt_devicepresent_state">D3DKMT_DEVICEPRESENT_STATE</a>
</dt>
<dt>
<a href="display.d3dkmt_devicereset_state">D3DKMT_DEVICERESET_STATE</a>
</dt>
<dt>
<a href="display.d3dkmt_devicestate_type">D3DKMT_DEVICESTATE_TYPE</a>
</dt>
<dt>
<a href="display.d3dkmtgetdevicestate">D3DKMTGetDeviceState</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_GETDEVICESTATE structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
