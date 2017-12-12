---
UID: NI.bthioctl.IOCTL_BTH_GET_RADIO_INFO
title: IOCTL_BTH_GET_RADIO_INFO
author: windows-driver-content
description: The IOCTL_BTH_GET_RADIO_INFO request obtains information about the specified remote radio.
old-location: bltooth\ioctl_bth_get_radio_info.htm
old-project: bltooth
ms.assetid: 45803e80-6090-4b64-8c92-6b5efebd1cfc
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1, HFP_BYPASS_CODEC_ID_V1
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
req.alt-api: IOCTL_BTH_GET_RADIO_INFO
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

# IOCTL_BTH_GET_RADIO_INFO IOCTL



## -description

The IOCTL_BTH_GET_RADIO_INFO request obtains information about the specified remote radio.



The IOCTL_BTH_GET_RADIO_INFO request obtains information about the specified remote radio.



## -ioctlparameters

### -input-buffer
<a id="Input_Buffer"></a><a id="input_buffer"></a><a id="INPUT_BUFFER"></a>Input Buffer
The 
      <b>AssociatedIrp.SystemBuffer</b> member specifies the Bluetooth address of the remote radio to
      query.</p>The 
      <b>AssociatedIrp.SystemBuffer</b>AssociatedIrp.SystemBuffer member specifies the Bluetooth address of the remote radio to
      query.


### -input-buffer-length

<text></text>

### -output-buffer
<a id="Output_Buffer"></a><a id="output_buffer"></a><a id="OUTPUT_BUFFER"></a>Output Buffer
The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that holds a 
      <a href="bltooth.bth_radio_info">BTH_RADIO_INFO</a> structure. This structure
      contains information about the remote radio's feature support for the Link Management Protocol (LMP),
      the radio's manufacturer ID, and its LMP version.</p>The 
      <b>AssociatedIrp.SystemBuffer</b>AssociatedIrp.SystemBuffer member points to a buffer that holds a 
      <a href="bltooth.bth_radio_info">BTH_RADIO_INFO</a><b>BTH_RADIO_INFO</b>BTH_RADIO_INFO structure. This structure
      contains information about the remote radio's feature support for the Link Management Protocol (LMP),
      the radio's manufacturer ID, and its LMP version.


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
<a id="I_O_Status_Block"></a><a id="i_o_status_block"></a><a id="I_O_STATUS_BLOCK"></a>I/O Status Block
If the request is successful, the 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the output
      buffer. Otherwise, the 
      <b>Information</b> member is set to zero.</p>If the request is successful, the 
      <b>Information</b>Information member of the STATUS_BLOCK structure is set to the size, in bytes, of the output
      buffer. Otherwise, the 
      <b>Information</b>Information member is set to zero.
The 
      <b>Status</b> member is set to one of the values in the following table.</p>The 
      <b>Status</b>Status member is set to one of the values in the following table.
<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td>
STATUS_SUCCESS

</td>
<td>
The IOCTL completed successfully.

</td>
</tr>
<tr>
<td>
STATUS_DEVICE_NOT_CONNECTED

</td>
<td>
The device object for the specified device was not connected.

</td>
</tr>
</table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<th>Status value</th>Status value
<th>Description</th>Description

<tr>
<td>
STATUS_SUCCESS

</td>
<td>
The IOCTL completed successfully.

</td>
</tr>
<td>
STATUS_SUCCESS

</td>
STATUS_SUCCESS</p>STATUS_SUCCESS

<td>
The IOCTL completed successfully.

</td>
The IOCTL completed successfully.</p>The IOCTL completed successfully.


<tr>
<td>
STATUS_DEVICE_NOT_CONNECTED

</td>
<td>
The device object for the specified device was not connected.

</td>
</tr>
<td>
STATUS_DEVICE_NOT_CONNECTED

</td>
STATUS_DEVICE_NOT_CONNECTED</p>STATUS_DEVICE_NOT_CONNECTED

<td>
The device object for the specified device was not connected.

</td>
The device object for the specified device was not connected.</p>The device object for the specified device was not connected.



 </p> 


## -remarks
The IOCTL_BTH_GET_RADIO_INFO IOCTL returns similar information as the IOCTL_BTH_GET_LOCAL_INFO IOCTL,
    but for a remote Bluetooth radio.


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
<dt>
<a href="bltooth.bth_radio_info">BTH_RADIO_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20IOCTL_BTH_GET_RADIO_INFO control code%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

