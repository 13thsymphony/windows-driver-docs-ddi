---
UID: NI.bthxddi.IOCTL_BTHX_SET_VERSION
title: IOCTL_BTHX_SET_VERSION
author: windows-driver-content
description: IOCTL_BTHX_SET_VERSION is used to inform the transport driver of the version of the extensibility interface being used.
old-location: bltooth\ioctl_bthx_set_version.htm
old-project: bltooth
ms.assetid: FE572606-8F47-4C40-BF74-24D5F667D2EC
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _BTHX_SCO_SUPPORT, PBTHX_SCO_SUPPORT, *PBTHX_SCO_SUPPORT, BTHX_SCO_SUPPORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthxddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_BTHX_SET_VERSION
req.alt-loc: BthXDDI.h
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

# IOCTL_BTHX_SET_VERSION IOCTL



## -description

IOCTL_BTHX_SET_VERSION is used to inform the transport driver of the version of the extensibility interface being used.



IOCTL_BTHX_SET_VERSION is used to inform the transport driver of the version of the extensibility interface being used.



## -ioctlparameters

### -input-buffer
Profile drivers should use KMDF and its <a href="kmdf.wdfrequestretrieveinputmemory">WdfRequestRetrieveInputMemory</a> method to retrieve input parameters.  For example, to get the input buffer:

<code>Status = WdfRequestRetrieveInputMemory(_Request, &amp;ReqInMemory);</code>

The buffer describes a <a href="bltooth.bthx_version">BTHX_VERSION</a> structure. 

Refer to the WDK Bluetooth samples for more information.


### -input-buffer-length
The length of the buffer is the size of the <b>BTHX_VERSION</b> structure.


### -output-buffer
None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The 
      <b>Information</b> member of the STATUS_BLOCK structure is set to zero because the Bluetooth driver
      stack returns no data with this IOCTL.

The 
      <b>Status</b> member is set to one of the values in the following table.

STATUS_SUCCESS

The IOCTL completed successfully.

 

Any unsuccessful NT status code prevents the driver from loading.


## -remarks
IOCTL_BTHX_SET_VERSION is a synchronous operation.

Only one version will be selected and set.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with  Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>BthXDDI.h</dt>
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