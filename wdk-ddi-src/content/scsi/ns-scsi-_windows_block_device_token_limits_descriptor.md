---
UID: NS:scsi._WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR
title: "_WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR"
author: windows-driver-content
description: The WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR structure is the third party copy descriptor for Windows systems.
old-location: storage\windows_block_device_token_limits_descriptor.htm
old-project: storage
ms.assetid: A4DB93FE-96ED-4E6D-B912-31C53AD000FF
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: scsi/PWINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR, *PWINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR, storage.windows_block_device_token_limits_descriptor, WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR structure [Storage Devices], scsi/WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR, PWINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR structure pointer [Storage Devices], _WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR, WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR, PWINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsi.h
req.include-header: Scsi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	scsi.h
apiname:
-	WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: "*PWINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR, WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR"
req.product: Windows 10 or later.
---

# _WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR structure
The <b>WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR</b> structure is the third party copy descriptor for Windows systems. This structure serves as the descriptor for the vital product data (VPD) third party copy page.

## Syntax
````
typedef struct _WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR {
  UCHAR DescriptorType[2];
  UCHAR DescriptorLength[2];
  UCHAR VendorSpecific[6];
  UCHAR MaximumRangeDescriptors[2];
  UCHAR MaximumInactivityTimer[4];
  UCHAR DefaultInactivityTimer[4];
  UCHAR MaximumTokenTransferSize[8];
  UCHAR OptimalTransferCount[8];
} WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR, *PWINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR;
````

## Members


`DefaultInactivityTimer`

The default value that is used by the copy provider when the <b>InactivityTimeout</b> of the <a href="..\scsi\ns-scsi-populate_token_header.md">POPULATE_TOKEN_HEADER</a> structure is set to 0.

`DescriptorLength`

The length of this structure starting with the <b>VendorSpecific</b> member.

`DescriptorType`

The descriptor type identifying this structure. The descriptor type is defined in <i>storport.h</i> as <b>BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR_TYPE_WINDOWS</b>.

`MaximumInactivityTimer`

The maximum available to specify as the timeout value in the <b>InactivityTimeout</b> member of the <a href="..\scsi\ns-scsi-populate_token_header.md">POPULATE_TOKEN_HEADER</a> structure.

`MaximumRangeDescriptors`

The maximum number of range descriptors that may be included along with the <a href="..\scsi\ns-scsi-populate_token_header.md">POPULATE_TOKEN_HEADER</a> or the <a href="..\scsi\ns-scsi-write_using_token_header.md">WRITE_USING_TOKEN_HEADER</a> structures.

`MaximumTokenTransferSize`

The maximum number of logical blocks that can be specified as a total of the block range descriptors in the <a href="..\scsi\ns-scsi-populate_token_header.md">POPULATE_TOKEN_HEADER</a> or the <a href="..\scsi\ns-scsi-write_using_token_header.md">WRITE_USING_TOKEN_HEADER</a> structures.

`OptimalTransferCount`

The optimal number of logical blocks, as a maximum, to specify as a total of the block range descriptors in the <a href="..\scsi\ns-scsi-populate_token_header.md">POPULATE_TOKEN_HEADER</a> or the <a href="..\scsi\ns-scsi-write_using_token_header.md">WRITE_USING_TOKEN_HEADER</a> structures. Offload data transfer performance may degrade if the transfer count is larger than this value.

`VendorSpecific`

Vendor specific bytes included in the descriptor. Windows applications must treat this member as reserved and ignore the reported value.

## Remarks
All multibyte values are in big endian format. Prior to evaluation, these values must be converted to match the endian format of the current platform.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Header** | scsi.h (include Scsi.h) |

## See Also

<a href="..\scsi\ns-scsi-write_using_token_header.md">WRITE_USING_TOKEN_HEADER</a>

<a href="..\scsi\ns-scsi-populate_token_header.md">POPULATE_TOKEN_HEADER</a>

<a href="..\scsi\ns-scsi-_vpd_third_party_copy_page.md">VPD_THIRD_PARTY_COPY_PAGE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20WINDOWS_BLOCK_DEVICE_TOKEN_LIMITS_DESCRIPTOR structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>