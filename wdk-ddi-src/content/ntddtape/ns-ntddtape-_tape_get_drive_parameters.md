---
UID : NS:ntddtape._TAPE_GET_DRIVE_PARAMETERS
title : "_TAPE_GET_DRIVE_PARAMETERS"
author : windows-driver-content
description : The TAPE_GET_DRIVE_PARAMETERS structure is used in conjunction with the IOCTL_TAPE_GET_DRIVE_PARAMS request to retrieve information about capabilities of the tape drive.
old-location : storage\tape_get_drive_parameters.htm
old-project : storage
ms.assetid : 2b1b196f-f012-4136-983e-8c8192bdbd2f
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : structs-tape_aa0e95ac-ea8b-4c88-abc0-7809cd538e26.xml, TAPE_GET_DRIVE_PARAMETERS structure [Storage Devices], storage.tape_get_drive_parameters, TAPE_GET_DRIVE_PARAMETERS, PTAPE_GET_DRIVE_PARAMETERS, *PTAPE_GET_DRIVE_PARAMETERS, _TAPE_GET_DRIVE_PARAMETERS, ntddtape/PTAPE_GET_DRIVE_PARAMETERS, ntddtape/TAPE_GET_DRIVE_PARAMETERS, PTAPE_GET_DRIVE_PARAMETERS structure pointer [Storage Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddtape.h
req.include-header : Ntddtape.h
req.target-type : Windows
req.target-min-winverclnt : 
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PTAPE_GET_DRIVE_PARAMETERS, TAPE_GET_DRIVE_PARAMETERS"
---

# _TAPE_GET_DRIVE_PARAMETERS structure
The TAPE_GET_DRIVE_PARAMETERS structure is used in conjunction with the <a href="..\ntddtape\ni-ntddtape-ioctl_tape_get_drive_params.md">IOCTL_TAPE_GET_DRIVE_PARAMS</a> request to retrieve information about capabilities of the tape drive.

## Syntax
````
typedef struct _TAPE_GET_DRIVE_PARAMETERS {
  BOOLEAN ECC;
  BOOLEAN Compression;
  BOOLEAN DataPadding;
  BOOLEAN ReportSetmarks;
  ULONG   DefaultBlockSize;
  ULONG   MaximumBlockSize;
  ULONG   MinimumBlockSize;
  ULONG   MaximumPartitionCount;
  ULONG   FeaturesLow;
  ULONG   FeaturesHigh;
  ULONG   EOTWarningZoneSize;
} TAPE_GET_DRIVE_PARAMETERS, *PTAPE_GET_DRIVE_PARAMETERS;
````

## Members


`Compression`

When set to <b>TRUE</b>, indicates that compression is enabled on a device that supports it. When compression is enabled, the device compresses data prior to writing it. When set to <b>FALSE</b>, compression is not enabled on the device.

`DataPadding`

When set to <b>TRUE</b>, indicates that data padding is enabled on a device that supports it. When padding is enabled, the device pads data with zeros to keep the tape streaming until data is ready. When set to <b>FALSE</b>, data padding is not enabled.

`DefaultBlockSize`

Indicates the default block size, in bytes.

`ECC`

When set to <b>TRUE</b>, indicates that the device uses hardware error correction.

`EOTWarningZoneSize`

Indicates the size in bytes of the early warning zone toward the end of the tape. The device returns a check condition when it enters the zone.

`FeaturesHigh`

Indicates the additional features supported by this drive if TAPE_DRIVE_HIGH_FEATURES is set in <b>FeaturesLow</b>. The miniport driver sets TAPE_DRIVE_<i>XXX</i> flags for features supported by the drive and clears flags for features not supported. Callers can use the TAPE_DRIVE_<i>XXX</i> masks defined in <i>minitape.h </i>to determine whether a drive supports a particular feature. 
<table>
<tr>
<th>Mask</th>
<th>Meaning</th>
</tr>
<tr>
<td>
TAPE_DRIVE_ABS_BLK_IMMED

</td>
<td>
The device moves the tape to a device-specific block address and returns as soon as the move begins.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_ABSOLUTE_BLK

</td>
<td>
The device moves the tape to a device specific block address.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_END_OF_DATA

</td>
<td>
The device moves the tape to the end-of-data marker in a partition.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_FILEMARKS

</td>
<td>
The device moves the tape forward (or backward) a specified number of filemarks.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_FORMAT

</td>
<td>
The device can format the media. 

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_FORMAT_IMMEDIATE

</td>
<td>
The device can format the media as an immediate command.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_HIGH_FEATURES

</td>
<td>
A bitmask that indicates those bits which correspond to high features. 

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_LOAD_UNLOAD

</td>
<td>
The device enables and disables the device for further operations.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_LOAD_UNLD_IMMED

</td>
<td>
The device supports immediate load and unload operations.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_LOCK_UNLOCK

</td>
<td>
The device enables and disables the tape ejection mechanism.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_LOCK_UNLK_IMMED

</td>
<td>
The device supports immediate lock and unlock operations.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_LOG_BLK_IMMED

</td>
<td>
The device moves the tape to a logical block address in a partition and returns as soon as the move begins.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_LOGICAL_BLK

</td>
<td>
The device moves the tape to a logical block address in a partition.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_RELATIVE_BLKS

</td>
<td>
The device moves the tape forward (or backward) a specified number of blocks.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_REVERSE_POSITION

</td>
<td>
The device moves the tape backward over blocks, filemarks, or setmarks.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_REWIND_IMMEDIATE

</td>
<td>
The device supports immediate rewind operation.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_SEQUENTIAL_FMKS

</td>
<td>
The device moves the tape forward (or backward) to the first occurrence of a specified number of consecutive filemarks.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_SEQUENTIAL_SMKS

</td>
<td>
The device moves the tape forward (or backward) to the first occurrence of a specified number of consecutive setmarks.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_SET_BLOCK_SIZE

</td>
<td>
The device supports setting the size of a fixed-length logical block or setting the variable-length block mode.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_SET_COMPRESSION

</td>
<td>
The device enables and disables hardware data compression.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_SET_ECC

</td>
<td>
The device enables and disables hardware error correction.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_SET_PADDING

</td>
<td>
The device enables and disables data padding.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_SET_REPORT_SMKS

</td>
<td>
The device enables and disables the reporting of setmarks.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_SETMARKS

</td>
<td>
The device moves the tape forward (or reverse) a specified number of setmarks.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_SPACE_IMMEDIATE

</td>
<td>
The device supports immediate spacing.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_TENSION

</td>
<td>
The device supports tape tensioning.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_TENSION_IMMED

</td>
<td>
The device supports immediate tape tensioning.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_WRITE_FILEMARKS

</td>
<td>
The device writes filemarks.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_WRITE_LONG_FMKS

</td>
<td>
The device writes long filemarks.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_WRITE_MARK_IMMED

</td>
<td>
The device supports immediate writing of short and long filemarks.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_WRITE_SETMARKS

</td>
<td>
The device writes setmarks.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_WRITE_SHORT_FMKS

</td>
<td>
The device writes short filemarks.

</td>
</tr>
</table>

`FeaturesLow`

Indicates the features supported by this drive. The miniport driver sets TAPE_DRIVE_<i>XXX</i> flags for features supported by the drive and clears flags for features not supported. Callers can use the TAPE_DRIVE_<i>XXX</i> masks defined in <i>minitape.h</i> to determine whether a drive supports a particular feature. The masks available are as follows:
<table>
<tr>
<th>Mask</th>
<th>Meaning</th>
</tr>
<tr>
<td>
TAPE_DRIVE_CLEAN_REQUESTS

</td>
<td>
The device can report whether it requires cleaning.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_COMPRESSION

</td>
<td>
The device supports hardware data compression.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_ECC

</td>
<td>
The device supports hardware error correction.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_EJECT_MEDIA

</td>
<td>
The device ejects the media. 

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_EOT_WZ_SIZE

</td>
<td>
The device can report the end of zone warning size. 

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_ERASE_BOP_ONLY

</td>
<td>
The device performs the erase operation from the beginning-of-partition marker only.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_ERASE_IMMEDIATE

</td>
<td>
The device performs an immediate erase operation ??  that is, it returns when the erase operation begins.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_ERASE_LONG

</td>
<td>
The device performs a long erase operation.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_ERASE_SHORT

</td>
<td>
The device performs a short erase operation.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_FIXED

</td>
<td>
The device creates fixed data partitions.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_FIXED_BLOCK

</td>
<td>
The device supports fixed-length block mode.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_INITIATOR

</td>
<td>
The device creates initiator-defined partitions.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_GET_ABSOLUTE_BLK

</td>
<td>
The device provides the current device-specific block address.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_GET_LOGICAL_BLK

</td>
<td>
The device provides the current logical block address (and logical tape partition).

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_PADDING

</td>
<td>
The device supports data padding.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_REPORT_SMKS

</td>
<td>
The device supports setmark reporting.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_RESERVED_BIT

</td>
<td>
A mask that identifies a reserved bit. Drivers must not set this bit. 

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_SELECT

</td>
<td>
The device creates select data partitions.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_SET_CMP_BOP_ONLY

</td>
<td>
The device only allows compression to be enabled when the read/write head is at the beginning of the partition.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_SET_EOT_WZ_SIZE

</td>
<td>
The device supports setting the end-of-medium warning size.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_TAPE_CAPACITY

</td>
<td>
The device returns the maximum capacity of the tape.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_TAPE_REMAINING

</td>
<td>
The device returns the remaining capacity of the tape.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_VARIABLE_BLOCK

</td>
<td>
The device supports variable-length block mode.

</td>
</tr>
<tr>
<td>
TAPE_DRIVE_WRITE_PROTECT

</td>
<td>
The device returns an error if the tape is write-enabled or write-protected.

</td>
</tr>
</table>

`MaximumBlockSize`

Indicates the maximum block size, in bytes, of either the tape device or the underlying host bus adapter (HBA), whichever is smaller.

`MaximumPartitionCount`

Indicates the maximum number of partitions the device supports.

`MinimumBlockSize`

Indicates the minimum block size, in bytes.

`ReportSetmarks`

When set to <b>TRUE</b>, indicates that reporting setmarks is enabled on a device that supports it. The device reports setmarks encountered during read or space operations. When set to <b>FALSE</b>, reporting setmarks is not enabled.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddtape.h (include Ntddtape.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567936">TapeMiniGetDriveParameters</a>

<a href="..\ntddtape\ni-ntddtape-ioctl_tape_get_drive_params.md">IOCTL_TAPE_GET_DRIVE_PARAMS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TAPE_GET_DRIVE_PARAMETERS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>