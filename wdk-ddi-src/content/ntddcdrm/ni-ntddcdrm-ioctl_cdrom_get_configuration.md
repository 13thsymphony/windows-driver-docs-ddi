---
UID: NI:ntddcdrm.IOCTL_CDROM_GET_CONFIGURATION
title: IOCTL_CDROM_GET_CONFIGURATION
author: windows-driver-content
description: Requests feature and profile information from a CD-ROM device.
old-location: storage\ioctl_cdrom_get_configuration.htm
old-project: storage
ms.assetid: 2eb4b5c3-db06-4d21-8937-847734d7ac2f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_cdrom_get_configuration, IOCTL_CDROM_GET_CONFIGURATION control code [Storage Devices], IOCTL_CDROM_GET_CONFIGURATION, ntddcdrm/IOCTL_CDROM_GET_CONFIGURATION, k307_355fe40f-4056-4bd7-8e79-8824c38589f6.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddcdrm.h
apiname:
-	IOCTL_CDROM_GET_CONFIGURATION
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_GET_CONFIGURATION IOCTL
Requests feature and profile information from a CD-ROM device. 

Multimedia devices have different characteristics depending on the type of media that is in the device. To provide drivers with a means of querying multimedia devices about these varying characteristics, the <i>SCSI Multimedia - 3</i> (<i>MMC-3</i>) specification defines a command called "GET CONFIGURATION." This command permits drivers to query a device for both permanent information about the device and information that varies whenever the media changes. In Microsoft Windows 2000 and later operating systems, drivers can send this query to a device using the IOCTL_CDROM_GET_CONFIGURATION request. 

The IOCTL_CDROM_GET_CONFIGURATION request returns a list of descriptors that describe the capabilities of the device for the current medium. These descriptors are divided into two groups called "feature descriptors" and "profile list descriptors." A feature specifies the capabilities of a device and its associated medium. A profile is a collection of features. If the device supports a profile, it supports all the features in the profile. 

See the <i>MMC-3</i> specification for further discussion concerning features and profiles.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
Input buffer.

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the IO_STACK_LOCATION structure indicates the size, in bytes, of the input buffer, which must be = <b>sizeof</b>(GET_CONFIGURATION_IOCTL_INPUT).

### Output Buffer
The driver returns the feature and profile data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The data begins with a header of type <a href="..\ntddmmc\ns-ntddmmc-_get_configuration_header.md">GET_CONFIGURATION_HEADER</a>. Feature data is reported in the space immediately following this header. Its size and formatting depend on which features are reported.

### Output Buffer Length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(GET_CONFIGURATION_HEADER).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the number of bytes that are returned. The <b>Status</b> field is set to STATUS_SUCCESS if the request succeeds. If the <b>Parameters.DeviceIoControl.InputBufferLength</b> does not have the correct value, the request fails with a STATUS_INFO_LENGTH_MISMATCH error. If <b>Parameters.DeviceIoControl.OutputBufferLength</b> is not large enough, the request fails with a STATUS_BUFFER_TOO_SMALL error. If the value for the output buffer is too large, the request fails a STATUS_INVALID_BUFFER_SIZE message.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddmmc\ns-ntddmmc-_get_configuration_header.md">GET_CONFIGURATION_HEADER</a>



<a href="..\ntddmmc\ns-ntddmmc-_get_configuration_ioctl_input.md">GET_CONFIGURATION_IOCTL_INPUT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CDROM_GET_CONFIGURATION control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>