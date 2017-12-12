---
UID: NS.WINBIO_IOCTL._WINBIO_UPDATE_FIRMWARE
title: _WINBIO_UPDATE_FIRMWARE
author: windows-driver-content
description: The WINBIO_UPDATE_FIRMWARE structure is the IN payload for IOCTL_BIOMETRIC_UPDATE_FIRMWARE.
old-location: biometric\winbio_update_firmware.htm
old-project: biometric
ms.assetid: 14775785-27e3-4bfa-ad69-695869ebb5d6
ms.author: windowsdriverdev
ms.date: 11/13/2017
ms.keywords: _WINBIO_UPDATE_FIRMWARE, WINBIO_UPDATE_FIRMWARE, *PWINBIO_UPDATE_FIRMWARE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winbio_ioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WINBIO_UPDATE_FIRMWARE
req.alt-loc: winbio_ioctl.h
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

# _WINBIO_UPDATE_FIRMWARE structure



## -description
The WINBIO_UPDATE_FIRMWARE structure is the IN payload for <a href="..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_update_firmware.md">IOCTL_BIOMETRIC_UPDATE_FIRMWARE</a>.



## -syntax

````
typedef struct _WINBIO_UPDATE_FIRMWARE {
  DWORD       PayloadSize;
  WINBIO_DATA FirmwareData;
} WINBIO_UPDATE_FIRMWARE, *PWINBIO_UPDATE_FIRMWARE;
````


## -struct-fields

### -field PayloadSize

Specifies the total size of the payload, which includes the fixed length structure and any variable data at the end.


### -field FirmwareData

Specifies a structure of type <a href="biometric.winbio_data">WINBIO_DATA</a> that contains the vendor-specific firmware image.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Winbio_ioctl.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_update_firmware.md">IOCTL_BIOMETRIC_UPDATE_FIRMWARE</a>
</dt>
<dt>
<a href="biometric.winbio_blank_payload">WINBIO_BLANK_PAYLOAD</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [biometric\biometric]:%20WINBIO_UPDATE_FIRMWARE structure%20 RELEASE:%20(11/13/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

