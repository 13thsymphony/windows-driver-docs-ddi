---
UID: NS:storduid._STORAGE_DEVICE_LAYOUT_SIGNATURE
title: _STORAGE_DEVICE_LAYOUT_SIGNATURE
author: windows-driver-content
description: The STORAGE_DEVICE_LAYOUT_SIGNATURE structure defines a device layout structure.
old-location: storage\storage_device_layout_signature.htm
old-project: storage
ms.assetid: 3c433fe5-1782-4a00-aa7b-1558b0f56080
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _STORAGE_DEVICE_LAYOUT_SIGNATURE, STORAGE_DEVICE_LAYOUT_SIGNATURE, *PSTORAGE_DEVICE_LAYOUT_SIGNATURE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storduid.h
req.include-header: Storduid.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_DEVICE_LAYOUT_SIGNATURE
req.alt-loc: storduid.h
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
req.typenames: STORAGE_DEVICE_LAYOUT_SIGNATURE, *PSTORAGE_DEVICE_LAYOUT_SIGNATURE
req.product: Windows 10 or later.
---

# _STORAGE_DEVICE_LAYOUT_SIGNATURE structure



## -description
The STORAGE_DEVICE_LAYOUT_SIGNATURE structure defines a device layout structure.



## -syntax

````
typedef struct _STORAGE_DEVICE_LAYOUT_SIGNATURE {
  ULONG   Version;
  ULONG   Size;
  BOOLEAN Mbr;
  union {
    ULONG MbrSignature;
    GUID  GptDiskId;
  } DeviceSpecific;
} STORAGE_DEVICE_LAYOUT_SIGNATURE, *PSTORAGE_DEVICE_LAYOUT_SIGNATURE;
````


## -struct-fields

### -field Version

The version of the DUID.


### -field Size

The size, in bytes, of this STORAGE_DEVICE_LAYOUT_SIGNATURE structure.


### -field Mbr

A Boolean value that indicates whether the partition table of the disk is formatted with a master boot record (MBR). If <b>TRUE</b>, the partition table of the disk is formatted with a master boot record (MBR). If <b>FALSE</b>, the disk has a GUID partition table (GPT).


### -field DeviceSpecific


### -field MbrSignature

The signature value, which uniquely identifies the disk.


### -field GptDiskId

The GUID that uniquely identifies the disk.

</dd>
</dl>

## -remarks
The device layout signature contributes to the definition of a device unique identifier (DUID). For more information about DUIDs, see the description of the <a href="..\storduid\ns-storduid-_storage_device_unique_identifier.md">STORAGE_DEVICE_UNIQUE_IDENTIFIER</a> structure.


## -see-also
<dl>
<dt>
<a href="..\storduid\ns-storduid-_storage_device_unique_identifier.md">STORAGE_DEVICE_UNIQUE_IDENTIFIER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_DEVICE_LAYOUT_SIGNATURE structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

