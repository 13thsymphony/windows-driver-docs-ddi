---
UID: NS:minitape._VPD_THIRD_PARTY_COPY_PAGE
title: "_VPD_THIRD_PARTY_COPY_PAGE"
author: windows-driver-content
description: The VPD_THIRD_PARTY_COPY_PAGE structure defines the vital product data (VPD) page for offload data transfer operations.
old-location: storage\vpd_third_party_copy_page.htm
old-project: storage
ms.assetid: E8D9E05C-26C3-474C-854F-9AD12C8834DF
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PVPD_THIRD_PARTY_COPY_PAGE, PVPD_THIRD_PARTY_COPY_PAGE, PVPD_THIRD_PARTY_COPY_PAGE structure pointer [Storage Devices], VPD_THIRD_PARTY_COPY_PAGE, VPD_THIRD_PARTY_COPY_PAGE structure [Storage Devices], _VPD_THIRD_PARTY_COPY_PAGE, scsi/PVPD_THIRD_PARTY_COPY_PAGE, scsi/VPD_THIRD_PARTY_COPY_PAGE, storage.vpd_third_party_copy_page"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: minitape.h
req.include-header: Scsi.h, Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	scsi.h
api_name:
-	VPD_THIRD_PARTY_COPY_PAGE
product: Windows
targetos: Windows
req.typenames: VPD_THIRD_PARTY_COPY_PAGE, *PVPD_THIRD_PARTY_COPY_PAGE
---

# _VPD_THIRD_PARTY_COPY_PAGE structure
The <b>VPD_THIRD_PARTY_COPY_PAGE</b> structure defines the vital product data (VPD) page for offload data transfer operations.

## Syntax
````
typedef struct _VPD_THIRD_PARTY_COPY_PAGE {
  UCHAR DeviceType  :5;
  UCHAR DeviceTypeQualifier  :3;
  UCHAR PageCode;
  UCHAR PageLength[2];
  UCHAR ThirdPartyCopyDescriptors[ANYSIZE_ARRAY];
} VPD_THIRD_PARTY_COPY_PAGE, *PVPD_THIRD_PARTY_COPY_PAGE;
````

## Members


`DeviceType`

The device type. This is the same device type defined for use in the inquiry data for the storage device.

`DeviceTypeQualifier`

A qualifier code for the device. Currently, <b>DEVICE_CONNECTED</b>, is the only valid value.

`PageCode`

The page code for the VPD third party copy page. This page code is defined as 0x8f.

`PageLength`

The length, in bytes, of the VPD page. For offload data transfer on Windows, <b>PageLength</b> must be &gt;= 0x24.

`ThirdPartyCopyDescriptors`

Support descriptors for copy operations. On Windows systems, <b>ThirdPartyCopyDescriptors</b>  will contain one descriptor formatted as a <a href="..\minitape\ns-minitape-_windows_block_device_token_limits_descriptor.md">WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR</a> structure.

## Remarks
All multibyte values are in big endian format. Prior to evaluation, these values must be converted to match the endian format of the current platform.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Header** | minitape.h (include Scsi.h, Minitape.h, Storport.h) |

## See Also

<a href="..\minitape\ns-minitape-_windows_block_device_token_limits_descriptor.md">WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20VPD_THIRD_PARTY_COPY_PAGE structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>