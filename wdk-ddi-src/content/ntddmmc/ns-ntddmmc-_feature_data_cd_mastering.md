---
UID: NS.NTDDMMC._FEATURE_DATA_CD_MASTERING
title: _FEATURE_DATA_CD_MASTERING
author: windows-driver-content
description: The FEATURE_DATA_CD_MASTERING structure holds information for the CD Mastering feature.
old-location: storage\feature_data_cd_mastering.htm
old-project: storage
ms.assetid: 340e9675-9d07-4224-ac1b-86e7586c0738
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _FEATURE_DATA_CD_MASTERING, *PFEATURE_DATA_CD_MASTERING, FEATURE_DATA_CD_MASTERING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddmmc.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FEATURE_DATA_CD_MASTERING
req.alt-loc: ntddmmc.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _FEATURE_DATA_CD_MASTERING structure



## -description
The FEATURE_DATA_CD_MASTERING structure holds information for the CD Mastering feature.


## -syntax

````
typedef struct _FEATURE_DATA_CD_MASTERING {
  FEATURE_HEADER Header;
  UCHAR          RWSubchannelsRecordable  :1;
  UCHAR          CdRewritable  :1;
  UCHAR          TestWriteOk  :1;
  UCHAR          RawRecordingOk  :1;
  UCHAR          RawMultiSessionOk  :1;
  UCHAR          SessionAtOnceOk  :1;
  UCHAR          BufferUnderrunFree  :1;
  UCHAR          Reserved1  :1;
  UCHAR          MaximumCueSheetLength[3];
} FEATURE_DATA_CD_MASTERING, *PFEATURE_DATA_CD_MASTERING;
````


## -struct-fields

### -field Header

Contains a <a href="storage.feature_header">FEATURE_HEADER</a> structure with header information for this feature descriptor. 

### -field RWSubchannelsRecordable

Indicates, when set to 1, that the device can record the R-W subchannels with user-supplied information. 

### -field CdRewritable

Indicates, when set to 1, that the device can do mastering and TAO recording on rewritable media. 

### -field TestWriteOk

Indicates, when set to 1, that the device can perform test writes. 

### -field RawRecordingOk

Indicates, when set to 1, that the device can record using the raw write type. 

### -field RawMultiSessionOk

Indicates, when set to 1, that the device can record multisession in raw mode. 

### -field SessionAtOnceOk

Indicates, when set to 1, that the device can record using the Session-at-Once recording mode. 

### -field BufferUnderrunFree

Indicates, when set to 1, that the device is capable of zero-loss linking.

### -field Reserved1

Reserved. 

### -field MaximumCueSheetLength

Indicates the maximum length of a Cue Sheet that can be accepted by the device for Session at Once recording. <b>MaximumCueSheetLength</b>[0] holds the most significant byte of the 3-byte value for the length. <b>MaximumCueSheetLength</b>[2] holds the least significant byte. 

## -remarks
This structure holds data for the feature named "CD Mastering" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can write to a CD in either "Session-at-Once" mode or Raw mode. 

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddmmc.h (include Ntddcdrm.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.feature_header">FEATURE_HEADER</a>
</dt>
<dt>
<a href="storage.feature_number">FEATURE_NUMBER</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_CD_MASTERING structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
