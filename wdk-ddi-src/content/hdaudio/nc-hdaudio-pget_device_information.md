---
UID: NC.hdaudio.PGET_DEVICE_INFORMATION
title: PGET_DEVICE_INFORMATION
author: windows-driver-content
description: The GetDeviceInformation routine retrieves information about the HD Audio controller device.The function pointer type for a GetDeviceInformation routine is defined as:
old-location: audio\getdeviceinformation.htm
old-project: audio
ms.assetid: bdd08133-0641-4eea-bfa3-75f700356132
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _SM_SetRNIDMgmtInfo_OUT, PSM_SetRNIDMgmtInfo_OUT, SM_SetRNIDMgmtInfo_OUT, *PSM_SetRNIDMgmtInfo_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetDeviceInformation
req.alt-loc: hdaudio.h
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
---

# PGET_DEVICE_INFORMATION callback



## -description
The <code>GetDeviceInformation</code> routine retrieves information about the HD Audio controller device.

The function pointer type for a <code>GetDeviceInformation</code> routine is defined as:



## -prototype

````
PGET_DEVICE_INFORMATION GetDeviceInformation;

NTSTATUS GetDeviceInformation(
  _In_    PVOID                       context,
  _Inout_ PHDAUDIO_DEVICE_INFORMATION deviceInformation
)
{ ... }
````


## -parameters

### -param context [in]

Specifies the context value from the <b>Context</b> member of the <a href="audio.hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a> or the <a href="audio.hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a> structure.


### -param deviceInformation [in, out]

Retrieves information about the HD Audio controller device. This parameter points to a caller-allocated <a href="audio.hdaudio_device_information">HDAUDIO_DEVICE_INFORMATION</a> structure into which the routine writes the device information.


## -returns
<code>GetDeviceInformation</code> returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows a possible return status code.
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>Indicates that the size specified at the beginning of the <i>deviceInformation</i> buffer is too small.

 


## -remarks
This routine retrieves device-dependent information that is static-that is, the information does not change dynamically over time.

The <i>deviceInformation</i> parameter is a pointer to a buffer that contains an HDAUDIO_DEVICE_INFORMATION structure into which the routine writes information about the HD Audio controller. Before calling <code>GetDeviceInformation</code>, the caller allocates the buffer and writes the buffer's size in bytes into the <b>Size</b> member at the beginning of the buffer.


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
<dt>Hdaudio.h (include Hdaudio.h)</dt>
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

## -see-also
<dl>
<dt>
<a href="audio.hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a>
</dt>
<dt>
<a href="audio.hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>
</dt>
<dt>
<a href="audio.hdaudio_device_information">HDAUDIO_DEVICE_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PGET_DEVICE_INFORMATION callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

