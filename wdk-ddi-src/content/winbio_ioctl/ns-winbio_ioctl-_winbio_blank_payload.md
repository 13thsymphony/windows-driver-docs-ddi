---
UID: NS:winbio_ioctl._WINBIO_BLANK_PAYLOAD
title: _WINBIO_BLANK_PAYLOAD
author: windows-driver-content
description: The IOCTL_BIOMETRIC_RESET and IOCTL_BIOMETRIC_UPDATE_FIRMWARE IOCTLs return the WINBIO_BLANK_PAYLOAD structure as output.
old-location: biometric\winbio_blank_payload.htm
old-project: biometric
ms.assetid: 0bc28853-1c00-42d3-a269-198093d64dd7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WINBIO_BLANK_PAYLOAD, *PWINBIO_BLANK_PAYLOAD, WINBIO_BLANK_PAYLOAD
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
req.alt-api: WINBIO_BLANK_PAYLOAD
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
req.typenames: *PWINBIO_BLANK_PAYLOAD, WINBIO_BLANK_PAYLOAD
req.product: Windows 10 or later.
---

# _WINBIO_BLANK_PAYLOAD structure



## -description
The <a href="..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_reset.md">IOCTL_BIOMETRIC_RESET</a> and <a href="..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_update_firmware.md">IOCTL_BIOMETRIC_UPDATE_FIRMWARE</a> IOCTLs return the WINBIO_BLANK_PAYLOAD structure as output.



## -syntax

````
typedef struct _WINBIO_BLANK_PAYLOAD {
  DWORD   PayloadSize;
  HRESULT WinBioHresult;
} WINBIO_BLANK_PAYLOAD, *PWINBIO_BLANK_PAYLOAD;
````


## -struct-fields

### -field PayloadSize

 The total size of the payload.  This includes the fixed length structure and any variable data at the end.


### -field WinBioHresult

The status detail of the I/O operation.  This is where WINBIO error and information codes will be passed. The following table shows possible values.

<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td>
S_OK

</td>
<td>
The operation completed successfully.

</td>
</tr>
<tr>
<td>
HRESULT_FROM_NT(STATUS_IO_DEVICE_ERROR)

</td>
<td>
The driver could not gather the necessary information from the device.

</td>
</tr>
<tr>
<td>
WINBIO_E_DEVICE_BUSY

</td>
<td>
The device is in the middle of a vendor-specific operation.  This should only be returned when the device cannot be reset, and the vendor-specific operation cannot be canceled.

</td>
</tr>
</table>
 


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