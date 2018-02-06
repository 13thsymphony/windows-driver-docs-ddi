---
UID: NS:ntddcdvd._DVD_COPY_PROTECT_KEY
title: "_DVD_COPY_PROTECT_KEY"
author: windows-driver-content
description: The DVD_COPY_PROTECT_KEY structure is used in conjunction with the IOCTL_DVD_READ_KEY request to execute a report key command of the specified type.
old-location: storage\dvd_copy_protect_key.htm
old-project: storage
ms.assetid: 79f3fdaf-e23a-40ba-a1eb-5428a63cc96a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "*PDVD_COPY_PROTECT_KEY, DVD_COPY_PROTECT_KEY, PDVD_COPY_PROTECT_KEY structure pointer [Storage Devices], ntddcdvd/DVD_COPY_PROTECT_KEY, DVD_COPY_PROTECT_KEY structure [Storage Devices], _DVD_COPY_PROTECT_KEY, ntddcdvd/PDVD_COPY_PROTECT_KEY, PDVD_COPY_PROTECT_KEY, structs-DVD_3ea6aa08-28ce-42d0-855d-d2e83ce58f89.xml, storage.dvd_copy_protect_key"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
-	ntddcdvd.h
apiname:
-	DVD_COPY_PROTECT_KEY
product: Windows
targetos: Windows
req.typenames: DVD_COPY_PROTECT_KEY, *PDVD_COPY_PROTECT_KEY
---

# _DVD_COPY_PROTECT_KEY structure
The <b>DVD_COPY_PROTECT_KEY</b> structure is used in conjunction with the <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_key.md">IOCTL_DVD_READ_KEY</a> request to execute a report key command of the specified type.

## Syntax
````
typedef struct _DVD_COPY_PROTECT_KEY {
  ULONG          KeyLength;
  DVD_SESSION_ID SessionId;
  DVD_KEY_TYPE   KeyType;
  ULONG          KeyFlags;
  union {
    HANDLE        FileHandle;
    LARGE_INTEGER TitleOffset;
  } Parameters;
  UCHAR          KeyData[];
} DVD_COPY_PROTECT_KEY, *PDVD_COPY_PROTECT_KEY;
````

## Members


`KeyData`

Contains the key data that was returned.

`KeyFlags`

####  This member can have any of the following values:



####

`KeyLength`

Indicates the length of the key data to be retrieved.

`KeyType`

Indicates the key type. The DVD device driver uses this information to determine the key format in a report key command, as defined by the <i>SCSI Multimedia Commands - 3 (MMC-3)</i> specification. A report key command either reports key data for a specified key (challenge key, bus key, title key, RPC key, or disk key), reports the state of the authentication success flag (ASF), or invalidates an authentication grant ID (AGID). See the <i>MMC-3</i> specification for further information.

`Parameters`



`SessionId`

Indicates the DVD session ID.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdvd.h (include Ntddcdvd.h) |

## See Also

<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_dvd_read_key.md">IOCTL_DVD_READ_KEY</a>

<a href="..\ntddcdvd\ne-ntddcdvd-dvd_key_type.md">DVD_KEY_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DVD_COPY_PROTECT_KEY structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>