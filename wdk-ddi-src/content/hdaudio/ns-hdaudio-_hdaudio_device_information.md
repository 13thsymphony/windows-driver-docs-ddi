---
UID: NS:hdaudio._HDAUDIO_DEVICE_INFORMATION
title: _HDAUDIO_DEVICE_INFORMATION
author: windows-driver-content
description: The HDAUDIO_DEVICE_INFORMATION structure specifies the hardware capabilities of the HD Audio bus controller.
old-location: audio\hdaudio_device_information.htm
old-project: audio
ms.assetid: 091aee9d-5ecd-481a-b5e2-28b4828b2c2e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _HDAUDIO_DEVICE_INFORMATION, *PHDAUDIO_DEVICE_INFORMATION, HDAUDIO_DEVICE_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HDAUDIO_DEVICE_INFORMATION
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
req.irql: PASSIVE_LEVEL.
req.typenames: *PHDAUDIO_DEVICE_INFORMATION, HDAUDIO_DEVICE_INFORMATION
---

# _HDAUDIO_DEVICE_INFORMATION structure



## -description
The HDAUDIO_DEVICE_INFORMATION structure specifies the hardware capabilities of the HD Audio bus controller.



## -syntax

````
typedef struct _HDAUDIO_DEVICE_INFORMATION {
  USHORT  Size;
  USHORT  DeviceVersion;
  USHORT  DriverVersion;
  USHORT  CodecsDetected;
  BOOLEAN IsStripingSupported;
} HDAUDIO_DEVICE_INFORMATION, *PHDAUDIO_DEVICE_INFORMATION;
````


## -struct-fields

### -field Size

Specifies the size in bytes of the HDAUDIO_DEVICE_INFORMATION structure.


### -field DeviceVersion

Specifies the HD Audio controller device version.


### -field DriverVersion

Specifies the HD Audio bus driver version.


### -field CodecsDetected

Specifies the number of codecs that the HD Audio controller detects on the HD Audio Link.


### -field IsStripingSupported

Specifies whether the HD Audio controller supports <a href="https://msdn.microsoft.com/29ab650c-0c3b-4693-a277-4d9ba63b7b66">striping</a>. If <b>TRUE</b>, it supports striping (with at least two SDO lines). If <b>FALSE</b>, it does not support striping.


## -remarks
The <a href="..\hdaudio\nc-hdaudio-pget_device_information.md">GetDeviceInformation</a> routine uses this structure to provide information about the HD Audio controller's device-specific capabilities to clients.


## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\hdaudio\nc-hdaudio-pget_device_information.md">GetDeviceInformation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20HDAUDIO_DEVICE_INFORMATION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

