---
UID: NI:bthioctl.IOCTL_BTH_GET_DEVICE_INFO
title: IOCTL_BTH_GET_DEVICE_INFO
author: windows-driver-content
description: The IOCTL_BTH_GET_DEVICE_INFO request returns information about all cached, previously discovered remote radios that are Bluetooth-enabled.
old-location: bltooth\ioctl_bth_get_device_info.htm
old-project: bltooth
ms.assetid: 99bc222f-9c27-45b7-ade1-2401dfa41d7c
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _HFP_BYPASS_CODEC_ID_V1, HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1
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
req.alt-api: IOCTL_BTH_GET_DEVICE_INFO
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
req.typenames: HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1
---

# IOCTL_BTH_GET_DEVICE_INFO IOCTL



## -description

The IOCTL_BTH_GET_DEVICE_INFO request returns information about all cached, previously discovered
     remote radios that are Bluetooth-enabled.



The IOCTL_BTH_GET_DEVICE_INFO request returns information about all cached, previously discovered
     remote radios that are Bluetooth-enabled.



## -ioctlparameters

### -input-buffer
The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer for a 
      <a href="..\bthioctl\ns-bthioctl-_bth_device_info_list.md">BTH_DEVICE_INFO_LIST</a> structure.


### -input-buffer-length
The length of a 
      <a href="..\bthioctl\ns-bthioctl-_bth_device_info_list.md">BTH_DEVICE_INFO_LIST</a> structure


### -output-buffer
The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that holds a 
      <a href="..\bthioctl\ns-bthioctl-_bth_device_info_list.md">BTH_DEVICE_INFO_LIST</a> structure. The 
      <b>numOfDevices</b> member of the BTH_DEVICE_INFO_LIST structure contains the number of devices for
      which there is information and an array of 
      <a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a> structures; one array
      entry for each device.


### -output-buffer-length
If the size of the passed output buffer is not exactly <code>sizeof(BTH_DEVICE_INFO_LIST)</code> plus the correct multiple of <code>sizeof(BTH_DEVICE_INFO)</code>, the request will fail with STATUS_INVALID_BUFFER_SIZE.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, the 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the buffer that
      holds information about the array of devices. The BTH_DEVICE_INFO_LIST structure contains storage for
      the first BTH_DEVICE_INFO structure, so if no devices are returned, the 
      <b>Information</b> member is set to the size of the first structure.

The 
      <b>Status</b> member is set to one of the values in the following table.

STATUS_SUCCESS

The IOCTL completed successfully.

STATUS_INVALID_PARAMETER

The input buffer passed in was <b>NULL</b>.

STATUS_INVALID_BUFFER_SIZE

The output buffer was not sized correctly.

 


## -remarks
The IOCTL_BTH_GET_DEVICE_INFO IOCTL provides information about all previously discovered remote
    radios.

The 
    <b>numOfDevices</b> member of the BTH_DEVICE_INFO_LIST structure returns the total number of
    BTH_DEVICE_INFO structures that are returned by the IOCTL. If the calling driver passes in a buffer that
    is smaller than the value of the 
    <b>numOfDevices</b> member, only a portion of the available structures will be returned. Bluetooth driver
    developers should call IOCTL_BTH_GET_DEVICE_INFO with a small buffer first, for example 
    <code>sizeof(BTH_DEVICE_INFO_LIST)</code>, and then use the returned 
    <b>numOfDevices</b> member to correctly size the buffer for a subsequent call.

The BTH_DEVICE_INFO_LIST structure includes storage for the first BTH_DEVICE_INFO structure. Use the
    following formula to calculate the correct buffer size for a call to IOCTL_BTH_GET_DEVICE_INFO: 
    <code>
    Buffer=sizeof(BTH_DEVICE_INFO_LIST)+(NumOfDevices-1)*sizeof(BTH_DEVICE_INFO)</code>.


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
<a href="..\bthioctl\ns-bthioctl-_bth_device_info_list.md">BTH_DEVICE_INFO_LIST</a>
</dt>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20IOCTL_BTH_GET_DEVICE_INFO control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

