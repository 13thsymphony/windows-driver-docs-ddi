---
UID : NI:bthioctl.IOCTL_BTH_GET_DEVICE_INFO
title : IOCTL_BTH_GET_DEVICE_INFO
author : windows-driver-content
description : The IOCTL_BTH_GET_DEVICE_INFO request returns information about all cached, previously discovered remote radios that are Bluetooth-enabled.
old-location : bltooth\ioctl_bth_get_device_info.htm
old-project : bltooth
ms.assetid : 99bc222f-9c27-45b7-ade1-2401dfa41d7c
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : bltooth.ioctl_bth_get_device_info, IOCTL_BTH_GET_DEVICE_INFO control code [Bluetooth Devices], IOCTL_BTH_GET_DEVICE_INFO, bthioctl/IOCTL_BTH_GET_DEVICE_INFO, bth_ioctls_427504e3-7414-4d2c-b835-b612ed73ce01.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : bthioctl.h
req.include-header : Bthioctl.h
req.target-type : Windows
req.target-min-winverclnt : Versions:\_Supported in Windows Vista, and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<= PASSIVE_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1
---

# IOCTL_BTH_GET_DEVICE_INFO IOCTL
The IOCTL_BTH_GET_DEVICE_INFO request returns information about all cached, previously discovered
     remote radios that are Bluetooth-enabled.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer for a 
      <a href="..\bthioctl\ns-bthioctl-_bth_device_info_list.md">BTH_DEVICE_INFO_LIST</a> structure.

### Input Buffer Length
The length of a 
      <a href="..\bthioctl\ns-bthioctl-_bth_device_info_list.md">BTH_DEVICE_INFO_LIST</a> structure

### Output Buffer
The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that holds a 
      <a href="..\bthioctl\ns-bthioctl-_bth_device_info_list.md">BTH_DEVICE_INFO_LIST</a> structure. The 
      <b>numOfDevices</b> member of the BTH_DEVICE_INFO_LIST structure contains the number of devices for
      which there is information and an array of 
      <a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a> structures; one array
      entry for each device.

### Output Buffer Length
If the size of the passed output buffer is not exactly <code>sizeof(BTH_DEVICE_INFO_LIST)</code> plus the correct multiple of <code>sizeof(BTH_DEVICE_INFO)</code>, the request will fail with STATUS_INVALID_BUFFER_SIZE.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the request is successful, the 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the buffer that
      holds information about the array of devices. The BTH_DEVICE_INFO_LIST structure contains storage for
      the first BTH_DEVICE_INFO structure, so if no devices are returned, the 
      <b>Information</b> member is set to the size of the first structure.

The 
      <b>Status</b> member is set to one of the values in the following table.
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
STATUS_INVALID_PARAMETER

</td>
<td>
The input buffer passed in was <b>NULL</b>.

</td>
</tr>
<tr>
<td>
STATUS_INVALID_BUFFER_SIZE

</td>
<td>
The output buffer was not sized correctly.

</td>
</tr>
</table>

## Remarks
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

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later. Versions:\_Supported in Windows Vista, and later. |
| **Header** | bthioctl.h (include Bthioctl.h) |
| **IRQL** | "<= PASSIVE_LEVEL" |

## See Also

<a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a>

<a href="..\bthioctl\ns-bthioctl-_bth_device_info_list.md">BTH_DEVICE_INFO_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20IOCTL_BTH_GET_DEVICE_INFO control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>