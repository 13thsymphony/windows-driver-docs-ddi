---
UID: NS.NTDDSCSI._STORAGE_DIAGNOSTIC_MP_REQUEST
title: _STORAGE_DIAGNOSTIC_MP_REQUEST
author: windows-driver-content
description: Describes a diagnostic request to Miniport. The STORAGE_DIAGNOSTIC_MP_REQUEST structure is provided in the input/output buffer of an IOCTL_SCSI_MINIPORT_DIAGNOSTIC request.
old-location: storage\storage_diagnostic_mp_request.htm
old-project: storage
ms.assetid: 1F2B15A6-7C05-4FBA-B54F-EEF013FF5739
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _STORAGE_DIAGNOSTIC_MP_REQUEST, STORAGE_DIAGNOSTIC_MP_REQUEST, *PSTORAGE_DIAGNOSTIC_MP_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddscsi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_DIAGNOSTIC_MP_REQUEST
req.alt-loc: ntddscsi.h
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

# _STORAGE_DIAGNOSTIC_MP_REQUEST structure



## -description
Describes  a diagnostic request to Miniport. The <b>STORAGE_DIAGNOSTIC_MP_REQUEST</b> structure is provided in the input/output buffer of an  <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport_diagnostic.md">IOCTL_SCSI_MINIPORT_DIAGNOSTIC</a> request.



## -syntax

````
typedef struct _STORAGE_DIAGNOSTIC_MP_REQUEST {
  ULONG                           Version;
  ULONG                           Size;
   STORAGE_DIAGNOSTIC_TARGET_TYPE TargetType;
  STORAGE_DIAGNOSTIC_LEVEL        Level;
  GUID                            ProviderId;
  ULONG                           BufferSize;
  ULONG                           Reserved;
   _Field_size_(BufferSize) UCHAR DataBuffer[ANYSIZE_ARRAY];
} STORAGE_DIAGNOSTIC_MP_REQUEST, *PSTORAGE_DIAGNOSTIC_MP_REQUEST;
````


## -struct-fields

### -field Version

Version of this structure.


### -field Size

Specifies the whole size of the structure and the associated data buffer.


### -field TargetType

Specifies the request target type. See definitions for <a href="storage.storage_diagnostic_target_type">STORAGE_DIAGNOSTIC_TARGET_TYPE</a>.


### -field Level

Specifies the Diagnostic level. See definitions for <a href="storage.storage_diagnostic_level">STORAGE_DIAGNOSTIC_LEVEL</a>.


### -field ProviderId

Specifies the GUID of the diagnostic data provider.


### -field BufferSize

Specifies the Data buffer size. As an input buffer, <i>BufferSize</i> should be set to number of bytes allocated for the <i>DataBuffer</i>. If the request is failed because of buffer too short, <i>BufferSize</i> should be set to the
       length required for <i>DataBuffer</i> by the diagnostic data provider;
       If the request is successful, it should be filled with returned data size of <i>DataBuffer</i>.       For other cases, it should be cleared to 0.


### -field Reserved

Reserved for future use.


### -field DataBuffer

Specifies the Diagnostic data buffer.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 10, version 1709.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddscsi.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_miniport_diagnostic.md">IOCTL_SCSI_MINIPORT_DIAGNOSTIC</a>
</dt>
<dt>
<a href="storage.storage_diagnostic_data">STORAGE_DIAGNOSTIC_DATA</a>
</dt>
<dt>
<a href="storage.storage_diagnostic_level">STORAGE_DIAGNOSTIC_LEVEL</a>
</dt>
<dt>
<a href="storage.storage_diagnostic_target_type">STORAGE_DIAGNOSTIC_TARGET_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_DIAGNOSTIC_MP_REQUEST structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

