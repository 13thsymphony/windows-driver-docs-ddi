---
UID: NI.bthioctl.IOCTL_INTERNAL_BTHENUM_GET_DEVINFO
title: IOCTL_INTERNAL_BTHENUM_GET_DEVINFO
author: windows-driver-content
description: The IOCTL_INTERNAL_BTHENUM_GET_DEVINFO request returns information about the remote device that caused the Plug and Play (PnP) manager to load the current instance of the profile driver.
old-location: bltooth\ioctl_internal_bthenum_get_devinfo.htm
old-project: bltooth
ms.assetid: c0134541-2e17-41e5-b30a-493b1bb42d07
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1, HFP_BYPASS_CODEC_ID_V1, PHFP_BYPASS_CODEC_ID_V1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_INTERNAL_BTHENUM_GET_DEVINFO
req.alt-loc: Bthioctl.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= PASSIVE_LEVEL
---

# IOCTL_INTERNAL_BTHENUM_GET_DEVINFO IOCTL



## -description

The IOCTL_INTERNAL_BTHENUM_GET_DEVINFO request returns information about the remote device that
     caused the Plug and Play (PnP) manager to load the current instance of the profile driver.



The IOCTL_INTERNAL_BTHENUM_GET_DEVINFO request returns information about the remote device that
     caused the Plug and Play (PnP) manager to load the current instance of the profile driver.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that holds a 
      <a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a> structure that
      contains information about the device's state, the device's address, and class of device (CoD).


### -output-buffer-length
The length of a 
      <a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a> structure.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, the 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the output
      buffer. Otherwise, the 
      <b>Information</b> member is set to zero.

The 
      <b>Status</b> member is set to one of the values in the following table.

STATUS_SUCCESS

The IOCTL completed successfully.

STATUS_INVALID_BUFFER_SIZE

The output buffer was sized incorrectly.

 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Versions: Supported in Windows Vista, and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Bthioctl.h (include Bthioctl.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20IOCTL_INTERNAL_BTHENUM_GET_DEVINFO control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

