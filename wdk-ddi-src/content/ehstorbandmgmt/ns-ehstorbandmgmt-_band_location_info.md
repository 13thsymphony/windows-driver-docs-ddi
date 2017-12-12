---
UID: NS.EHSTORBANDMGMT._BAND_LOCATION_INFO
title: _BAND_LOCATION_INFO
author: windows-driver-content
description: The BAND_LOCATION_INFO structure specifies the location information for a band table entry query.
old-location: storage\band_location_info.htm
old-project: storage
ms.assetid: A9E28600-45B2-4082-917F-29B3237DEC84
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _BAND_LOCATION_INFO, BAND_LOCATION_INFO, *PBAND_LOCATION_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BAND_LOCATION_INFO
req.alt-loc: EhStorBandMgmt.h
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
---

# _BAND_LOCATION_INFO structure



## -description
The <b>BAND_LOCATION_INFO</b> structure specifies the location information for a band table entry query.



## -syntax

````
typedef struct _BAND_LOCATION_INFO {
  ULONG         StructSize;
  ULONG         Reserved;
  LARGE_INTEGER BandStart;
  LARGE_INTEGER BandSize;
  BYTE          Metadata[32];
} BAND_LOCATION_INFO, *PBAND_LOCATION_INFO;
````


## -struct-fields

### -field StructSize

The size of the structure in bytes. Set to <b>sizeof</b>(BAND_LOCATION_INFO).


### -field Reserved

Reserved.


### -field BandStart

The offset in bytes of this band location on the storage device. This value is always 0 for the global band.


### -field BandSize

The size in bytes of the band configured at this location. This value is set to the maximum size possible for the global band.


### -field Metadata

A metadata field used as a data area for a band management application.


## -remarks
<b>BandStart</b> and <b>BandSize</b> must be a multiple of the sector size of the underlying storage device.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 8

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>EhStorBandMgmt.h (include EhStorBandMgmt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.band_table_entry">BAND_TABLE_ENTRY</a>
</dt>
<dt>
<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_create_band.md">IOCTL_EHSTOR_BANDMGMT_CREATE_BAND</a>
</dt>
<dt>
<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_enumerate_bands.md">IOCTL_EHSTOR_BANDMGMT_ENUMERATE_BANDS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20BAND_LOCATION_INFO structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

