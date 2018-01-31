---
UID : NE:ntddcdvd.DVD_KEY_TYPE
title : DVD_KEY_TYPE
author : windows-driver-content
description : The DVD_KEY_TYPE enumeration type is used in conjunction with the DVD_COPY_PROTECT_KEY structure to indicate a key to be read, to invalidate an authentication grant ID (AGID), and to request state information or region settings.
old-location : storage\dvd_key_type.htm
old-project : storage
ms.assetid : ec080043-a147-4002-8d0c-ed383182ec40
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : ntddcdvd/DvdSetRpcKey, storage.dvd_key_type, ntddcdvd/DvdAsf, DVD_KEY_TYPE, ntddcdvd/DvdDiskKey, DvdGetRpcKey, ntddcdvd/DvdGetRpcKey, ntddcdvd/DvdTitleKey, ntddcdvd/DvdChallengeKey, DvdSetRpcKey, ntddcdvd/DvdBusKey1, DvdBusKey1, ntddcdvd/DvdBusKey2, DvdAsf, DVD_KEY_TYPE enumeration [Storage Devices], structs-DVD_922c1979-c628-441b-b8e9-5818f6ed737d.xml, DvdBusKey2, DvdTitleKey, ntddcdvd/DVD_KEY_TYPE, DvdChallengeKey, DvdDiskKey, ntddcdvd/DvdInvalidateAGID, DvdInvalidateAGID
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntddcdvd.h
req.include-header : Ntddcdvd.h
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
req.typenames : DVD_KEY_TYPE
---

# DVD_KEY_TYPE Enumeration
The DVD_KEY_TYPE enumeration type is used in conjunction with the <a href="..\ntddcdvd\ns-ntddcdvd-_dvd_copy_protect_key.md">DVD_COPY_PROTECT_KEY</a> structure to indicate a key to be read, to invalidate an authentication grant ID (AGID), and to request state information or region settings.

## Syntax
````
typedef enum  { 
  DvdChallengeKey    = 0x01,
  DvdBusKey1         = 0x2,
  DvdBusKey2         = 0x3,
  DvdTitleKey        = 0x4,
  DvdAsf             = 0x5,
  DvdSetRpcKey       = 0x6,
  DvdGetRpcKey       = 0x8,
  DvdDiskKey         = 0x80,
  DvdInvalidateAGID  = 0x3f
} DVD_KEY_TYPE;
````

## Constants

<table>

<tr>
<td>DvdAsf</td>
<td>Gets the current state of the authentication success flag (ASF).</td>
</tr>

<tr>
<td>DvdBusKey1</td>
<td>Gets the first bus key.</td>
</tr>

<tr>
<td>DvdBusKey2</td>
<td>Gets the second bus key.</td>
</tr>

<tr>
<td>DvdChallengeKey</td>
<td>Gets a challenge key. This is used during the authentication key exchange process.</td>
</tr>

<tr>
<td>DvdDiskKey</td>
<td>Gets the disc key.</td>
</tr>

<tr>
<td>DvdGetRpcKey</td>
<td>Gets the region playback contents (RPC) for the logical unit.</td>
</tr>

<tr>
<td>DvdInvalidateAGID</td>
<td>Invalidates the specified authentication grant ID (AGID).</td>
</tr>

<tr>
<td>DvdSetRpcKey</td>
<td>Sets the region playback contents (RPC) for the logical unit.</td>
</tr>

<tr>
<td>DvdTitleKey</td>
<td>Gets a title key that is obfuscated by a bus key.</td>
</tr>
</table>

## Remarks

The driver for the DVD device uses the key type specified in this enumeration type to determine the key format in a report key command, as defined by the <i>SCSI Multimedia Commands - 3 (MMC-3) </i>specification. A report key command can either report key data for a specified key (challenge key, bus key, title key, RPC key, or disc key), or the state of the ASF flag. It can also invalidate an AGID. See the <i>MMC-3 </i>specification for further information. 

Drivers can issue a report key command to retrieve key data by means of an <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_key.md">IOCTL_DVD_READ_KEY</a> request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddcdvd.h (include Ntddcdvd.h) |

## See Also

<a href="..\ntddcdvd\ns-ntddcdvd-_dvd_copy_protect_key.md">DVD_COPY_PROTECT_KEY</a>

<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_send_key.md">IOCTL_DVD_SEND_KEY</a>

<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_key.md">IOCTL_DVD_READ_KEY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DVD_KEY_TYPE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>