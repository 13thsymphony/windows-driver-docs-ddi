---
UID: NS.winbio_ioctl._WINBIO_DIAGNOSTICS
title: WINBIO_DIAGNOSTICS
author: windows-driver-content
description: The IOCTL_BIOMETRIC_GET_SENSOR_STATUS IOCTL returns the WINBIO_DIAGNOSTICS structure as output.
old-location: biometric\winbio_diagnostics.htm
old-project: biometric
ms.assetid: 06f6abf1-9b44-4cf3-96d3-2017e0f6adda
ms.author: windowsdriverdev
ms.date: 11/13/2017
ms.keywords: WINBIO_DIAGNOSTICS, WINBIO_DIAGNOSTICS, *PWINBIO_DIAGNOSTICS
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
req.alt-api: WINBIO_DIAGNOSTICS
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
req.iface: IWiaTransferCallback
req.product: Windows 10 or later.
---

# WINBIO_DIAGNOSTICS structure



## -description
<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/ff536436">IOCTL_BIOMETRIC_GET_SENSOR_STATUS</a> IOCTL returns the WINBIO_DIAGNOSTICS structure as output.</p>


## -syntax

````
typedef struct _WINBIO_DIAGNOSTICS {
  DWORD                PayloadSize;
  HRESULT              WinBioHresult;
  WINBIO_SENSOR_STATUS SensorStatus;
  WINBIO_DATA          VendorDiagnostics;
} WINBIO_DIAGNOSTICS, *PWINBIO_DIAGNOSTICS;
````


## -struct-fields
<dl>

### -field <b>PayloadSize</b>

<dd>
<p>The total size of the payload.  This includes the fixed length structure and any variable data at the end.</p>
</dd>

### -field <b>WinBioHresult</b>

<dd>
<p>The status detail of the I/O operation.  This is where WINBIO error and information codes will be passed. The following table shows possible values.</p>
<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td>
<p>S_OK</p>
</td>
<td>
<p>The operation completed successfully.</p>
</td>
</tr>
<tr>
<td>
<p>HRESULT_FROM_NT(STATUS_IO_DEVICE_ERROR)</p>
</td>
<td>
<p>The driver could not gather the necessary information from the device.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field <b>SensorStatus</b>

<dd>
<p>A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff536476">WINBIO_SENSOR_STATUS</a> that contains the operating status of the biometric sensor.</p>
</dd>

### -field <b>VendorDiagnostics</b>

<dd>
<p>An optional <a href="https://msdn.microsoft.com/library/windows/hardware/ff536469">WINBIO_DATA</a> structure for vendor-specific additional information.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 7 and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536436">IOCTL_BIOMETRIC_GET_SENSOR_STATUS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [biometric\biometric]:%20WINBIO_DIAGNOSTICS structure%20 RELEASE:%20(11/13/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
