---
UID: NS.NTDDSTOR._STORAGE_DIAGNOSTIC_DATA
title: _STORAGE_DIAGNOSTIC_DATA
author: windows-driver-content
description: Describes diagnostic data about the storage driver stack. The STORAGE_DIAGNOSTIC_DATA structure is provided in the output buffer of an IOCTL_STORAGE_DIAGNOSTIC request.
old-location: storage\storage_diagnostic_data.htm
old-project: storage
ms.assetid: 68BC990B-DD0C-49CD-95EC-672FD1459B39
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _STORAGE_DIAGNOSTIC_DATA, *PSTORAGE_DIAGNOSTIC_DATA, PSTORAGE_DIAGNOSTIC_DATA, STORAGE_DIAGNOSTIC_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STORAGE_DIAGNOSTIC_DATA
req.alt-loc: ntddstor.h
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

# _STORAGE_DIAGNOSTIC_DATA structure



## -description
Describes  diagnostic data about the storage driver stack. The <b>STORAGE_DIAGNOSTIC_DATA</b> structure is provided in the output buffer of an  <a href="https://msdn.microsoft.com/5F71CCBE-F93F-4DCD-A673-1D6DE49C7400">IOCTL_STORAGE_DIAGNOSTIC</a> request.



## -syntax

````
typedef struct _STORAGE_DIAGNOSTIC_DATA {
  ULONG                          Version;
  ULONG                          Size;
  GUID                           ProviderId;
   ULONG                         BufferSize;
  ULONG                          Reserved;
  _Field_size_(BufferSize) UCHAR DiagnosticDataBuffer[ANYSIZE_ARRAY];
} STORAGE_DIAGNOSTIC_DATA, *PSTORAGE_DIAGNOSTIC_DATA;
````


## -struct-fields

### -field Version

Version of this structure.


### -field Size

Specifies the whole size of the structure and the associated data buffer.


### -field ProviderId

Specifies the GUID of a diagnostic data provider.


### -field BufferSize

If the request failed because of buffer too small, this field should be filled with the required buffer
    size for a <i>DiagnosticDataBuffer</i> needed by provider;
     if the request is successful, it should be filled with returned buffer size of <i>DiagnosticDataBuffer</i>;
     it should be cleared to zero for other cases.


### -field Reserved

Reserved for future use.


### -field DiagnosticDataBuffer

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
<dt>Ntddstor.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.storage_diagnostic_request">STORAGE_DIAGNOSTIC_REQUEST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/5F71CCBE-F93F-4DCD-A673-1D6DE49C7400">IOCTL_STORAGE_DIAGNOSTIC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_DIAGNOSTIC_DATA structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

