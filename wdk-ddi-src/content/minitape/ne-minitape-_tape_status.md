---
UID : NE:minitape._TAPE_STATUS
title : "_TAPE_STATUS"
author : windows-driver-content
description : The TAPE_STATUS enumeration provides a list of the status codes that the tape class driver uses to report the status of a tape device.
old-location : storage\tape_status.htm
old-project : storage
ms.assetid : 45e85ad1-5b75-410e-b9dd-061051bbaa74
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : minitape/PTAPE_STATUS, minitape/TAPE_STATUS_CALLBACK, TAPE_STATUS_NO_DATA_DETECTED, *PTAPE_STATUS, minitape/TAPE_STATUS_SETMARK_DETECTED, TAPE_STATUS enumeration [Storage Devices], minitape/TAPE_STATUS_REQUIRES_CLEANING, minitape/TAPE_STATUS_FILEMARK_DETECTED, TAPE_STATUS, TAPE_STATUS_DEVICE_NOT_READY, TAPE_STATUS_DATA_OVERRUN, TAPE_STATUS_EOM_OVERFLOW, minitape/TAPE_STATUS_BEGINNING_OF_MEDIA, minitape/TAPE_STATUS_END_OF_MEDIA, TAPE_STATUS_IO_DEVICE_ERROR, storage.tape_status, TAPE_STATUS_DEVICE_BUSY, minitape/TAPE_STATUS, TAPE_STATUS_MEDIA_WRITE_PROTECTED, minitape/TAPE_STATUS_INVALID_PARAMETER, minitape/TAPE_STATUS_DEVICE_BUSY, TAPE_STATUS_CALLBACK, minitape/TAPE_STATUS_DEVICE_NOT_READY, minitape/TAPE_STATUS_IO_DEVICE_ERROR, minitape/TAPE_STATUS_INVALID_BLOCK_LENGTH, TAPE_STATUS_CLEANER_CARTRIDGE_INSTALLED, minitape/TAPE_STATUS_CLEANER_CARTRIDGE_INSTALLED, structs-tape_c79a2dd4-8c91-4735-9440-de39b23aa982.xml, TAPE_STATUS_INVALID_BLOCK_LENGTH, TAPE_STATUS_REQUIRES_CLEANING, PTAPE_STATUS enumeration pointer [Storage Devices], minitape/TAPE_STATUS_CHECK_TEST_UNIT_READY, TAPE_STATUS_NO_SUCH_DEVICE, minitape/TAPE_STATUS_DEVICE_NOT_CONNECTED, minitape/TAPE_STATUS_NO_DATA_DETECTED, TAPE_STATUS_DEVICE_DATA_ERROR, minitape/TAPE_STATUS_DEVICE_DATA_ERROR, TAPE_STATUS_BEGINNING_OF_MEDIA, TAPE_STATUS_SETMARK_DETECTED, TAPE_STATUS_MEDIA_CHANGED, minitape/TAPE_STATUS_NO_SUCH_DEVICE, minitape/TAPE_STATUS_SEND_SRB_AND_CALLBACK, TAPE_STATUS_END_OF_MEDIA, minitape/TAPE_STATUS_IO_TIMEOUT, TAPE_STATUS_IO_TIMEOUT, minitape/TAPE_STATUS_MEDIA_WRITE_PROTECTED, TAPE_STATUS_SEND_SRB_AND_CALLBACK, TAPE_STATUS_BUFFER_OVERFLOW, TAPE_STATUS_SUCCESS, TAPE_STATUS_FILEMARK_DETECTED, minitape/TAPE_STATUS_SUCCESS, minitape/TAPE_STATUS_EOM_OVERFLOW, minitape/TAPE_STATUS_DATA_OVERRUN, TAPE_STATUS_UNRECOGNIZED_MEDIA, TAPE_STATUS_CHECK_TEST_UNIT_READY, minitape/TAPE_STATUS_BUFFER_OVERFLOW, minitape/TAPE_STATUS_NOT_IMPLEMENTED, TAPE_STATUS_INVALID_DEVICE_REQUEST, PTAPE_STATUS, TAPE_STATUS_BUS_RESET, _TAPE_STATUS, minitape/TAPE_STATUS_INVALID_DEVICE_REQUEST, minitape/TAPE_STATUS_INSUFFICIENT_RESOURCES, minitape/TAPE_STATUS_UNRECOGNIZED_MEDIA, TAPE_STATUS_DEVICE_NOT_CONNECTED, minitape/TAPE_STATUS_MEDIA_CHANGED, TAPE_STATUS_NOT_IMPLEMENTED, TAPE_STATUS_NO_MEDIA, TAPE_STATUS_INVALID_PARAMETER, minitape/TAPE_STATUS_BUS_RESET, TAPE_STATUS_INSUFFICIENT_RESOURCES, minitape/TAPE_STATUS_NO_MEDIA
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : minitape.h
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
req.typenames : "*PTAPE_STATUS, TAPE_STATUS"
---

# _TAPE_STATUS Enumeration
The TAPE_STATUS enumeration provides a list of the status codes that the tape class driver uses to report the status of a tape device.

## Syntax
````
typedef enum _TAPE_STATUS { 
  TAPE_STATUS_SEND_SRB_AND_CALLBACK        = 0,
  TAPE_STATUS_CALLBACK                     = 1,
  TAPE_STATUS_CHECK_TEST_UNIT_READY        = 2,
  TAPE_STATUS_SUCCESS                      = 3,
  TAPE_STATUS_INSUFFICIENT_RESOURCES       = 4,
  TAPE_STATUS_NOT_IMPLEMENTED              = 5,
  TAPE_STATUS_INVALID_DEVICE_REQUEST       = 6,
  TAPE_STATUS_INVALID_PARAMETER            = 7,
  TAPE_STATUS_MEDIA_CHANGED                = 8,
  TAPE_STATUS_BUS_RESET                    = 9,
  TAPE_STATUS_SETMARK_DETECTED             = 10,
  TAPE_STATUS_FILEMARK_DETECTED            = 11,
  TAPE_STATUS_BEGINNING_OF_MEDIA           = 12,
  TAPE_STATUS_END_OF_MEDIA                 = 13,
  TAPE_STATUS_BUFFER_OVERFLOW              = 14,
  TAPE_STATUS_NO_DATA_DETECTED             = 15,
  TAPE_STATUS_EOM_OVERFLOW                 = 16,
  TAPE_STATUS_NO_MEDIA                     = 17,
  TAPE_STATUS_IO_DEVICE_ERROR              = 18,
  TAPE_STATUS_UNRECOGNIZED_MEDIA           = 19,
  TAPE_STATUS_DEVICE_NOT_READY             = 20,
  TAPE_STATUS_MEDIA_WRITE_PROTECTED        = 21,
  TAPE_STATUS_DEVICE_DATA_ERROR            = 22,
  TAPE_STATUS_NO_SUCH_DEVICE               = 23,
  TAPE_STATUS_INVALID_BLOCK_LENGTH         = 24,
  TAPE_STATUS_IO_TIMEOUT                   = 25,
  TAPE_STATUS_DEVICE_NOT_CONNECTED         = 26,
  TAPE_STATUS_DATA_OVERRUN                 = 27,
  TAPE_STATUS_DEVICE_BUSY                  = 28,
  TAPE_STATUS_REQUIRES_CLEANING            = 29,
  TAPE_STATUS_CLEANER_CARTRIDGE_INSTALLED  = 30
} TAPE_STATUS, *PTAPE_STATUS;
````

## Constants

<table>

<tr>
<td>TAPE_STATUS_BEGINNING_OF_MEDIA</td>
<td>Indicates that the beginning of the media was encountered during a tape operation.</td>
</tr>

<tr>
<td>TAPE_STATUS_BUFFER_OVERFLOW</td>
<td>Indicates that a buffer overflow occurred.</td>
</tr>

<tr>
<td>TAPE_STATUS_BUS_RESET</td>
<td>Indicates that the bus has been reset.</td>
</tr>

<tr>
<td>TAPE_STATUS_CALLBACK</td>
<td>Directs the tape class driver to increment the call number counter without sending an SRB to the device. For more information about how tape miniclass drivers should make use of this status value, see <a href="https://msdn.microsoft.com/de6edfc6-9b4b-4866-8fdb-1047b43163de">Processing Tape Device Control Requests</a>.</td>
</tr>

<tr>
<td>TAPE_STATUS_CHECK_TEST_UNIT_READY</td>
<td>Directs the tape class driver to create an SRB for the TEST UNIT READY command and to send the SRB to the device.</td>
</tr>

<tr>
<td>TAPE_STATUS_CLEANER_CARTRIDGE_INSTALLED</td>
<td>Indicates that the media currently in the drive is a cleaner cartridge.</td>
</tr>

<tr>
<td>TAPE_STATUS_DATA_OVERRUN</td>
<td>Indicates that the tape operation could not be performed because of a data overrun.</td>
</tr>

<tr>
<td>TAPE_STATUS_DEVICE_BUSY</td>
<td>Indicates that the tape operation could not be performed, because the device is busy.</td>
</tr>

<tr>
<td>TAPE_STATUS_DEVICE_DATA_ERROR</td>
<td>Indicates that a cyclic redundancy check (CRC) error occurred.</td>
</tr>

<tr>
<td>TAPE_STATUS_DEVICE_NOT_CONNECTED</td>
<td>Indicates that the device is disconnected.</td>
</tr>

<tr>
<td>TAPE_STATUS_DEVICE_NOT_READY</td>
<td>Indicates that the device is not ready.</td>
</tr>

<tr>
<td>TAPE_STATUS_END_OF_MEDIA</td>
<td>Indicates that the end of the media was encountered during a tape operation.</td>
</tr>

<tr>
<td>TAPE_STATUS_EOM_OVERFLOW</td>
<td>Indicates that an attempt was made to exceed the physical end of the media during a tape operation.</td>
</tr>

<tr>
<td>TAPE_STATUS_FILEMARK_DETECTED</td>
<td>Indicates that a filemark was encountered during a tape operation.</td>
</tr>

<tr>
<td>TAPE_STATUS_INSUFFICIENT_RESOURCES</td>
<td>Indicates that there were not enough resources available to the miniclass driver for it to complete the operation.</td>
</tr>

<tr>
<td>TAPE_STATUS_INVALID_BLOCK_LENGTH</td>
<td>Indicates that the block length is invalid.</td>
</tr>

<tr>
<td>TAPE_STATUS_INVALID_DEVICE_REQUEST</td>
<td>Indicates that the requested operation is invalid.</td>
</tr>

<tr>
<td>TAPE_STATUS_INVALID_PARAMETER</td>
<td>Indicates that one or more of the parameter values provided with the request are invalid.</td>
</tr>

<tr>
<td>TAPE_STATUS_IO_DEVICE_ERROR</td>
<td>Indicates that an I/O error occurred during a tape operation.</td>
</tr>

<tr>
<td>TAPE_STATUS_IO_TIMEOUT</td>
<td>Indicates that the I/O operation timed out.</td>
</tr>

<tr>
<td>TAPE_STATUS_MEDIA_CHANGED</td>
<td>Indicates that the media in the drive might have changed.</td>
</tr>

<tr>
<td>TAPE_STATUS_MEDIA_WRITE_PROTECTED</td>
<td>Indicates that the media is write protected.</td>
</tr>

<tr>
<td>TAPE_STATUS_NO_DATA_DETECTED</td>
<td>Indicates that no data was detected.</td>
</tr>

<tr>
<td>TAPE_STATUS_NO_MEDIA</td>
<td>Indicates that the tape operation failed, because there is no media in the drive.</td>
</tr>

<tr>
<td>TAPE_STATUS_NO_SUCH_DEVICE</td>
<td>Indicates that no such device exists.</td>
</tr>

<tr>
<td>TAPE_STATUS_NOT_IMPLEMENTED</td>
<td>Indicates that the requested operation is not supported.</td>
</tr>

<tr>
<td>TAPE_STATUS_REQUIRES_CLEANING</td>
<td>Indicates that the tape operation could not be performed because the device requires cleaning.</td>
</tr>

<tr>
<td>TAPE_STATUS_SEND_SRB_AND_CALLBACK</td>
<td>Directs the tape class driver to send the SRB to the device. A tape miniclass routine usually returns this status after filling in the SRB passed by the tape class driver. If the operation is successful, the class driver increments a counter called a "call number" and calls the miniclass routine again. If the SRB fails, the class driver might call the miniclass routine again. For more information about how and when tape miniclass drivers should report this status value, see <a href="https://msdn.microsoft.com/de6edfc6-9b4b-4866-8fdb-1047b43163de">Processing Tape Device Control Requests</a>.</td>
</tr>

<tr>
<td>TAPE_STATUS_SETMARK_DETECTED</td>
<td>Indicates that a setmark was encountered during a tape operation.</td>
</tr>

<tr>
<td>TAPE_STATUS_SUCCESS</td>
<td>Indicates that the operation was successful.</td>
</tr>

<tr>
<td>TAPE_STATUS_UNRECOGNIZED_MEDIA</td>
<td>Indicates that the type of the media is not supported.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | minitape.h (include Ntddtape.h) |

## See Also

<a href="..\ntddtape\ni-ntddtape-ioctl_tape_get_status.md">IOCTL_TAPE_GET_STATUS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20TAPE_STATUS enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>