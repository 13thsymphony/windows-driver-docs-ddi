---
UID: NS.ntddk._WHEA_PERSISTENCE_INFO
title: WHEA_PERSISTENCE_INFO
author: windows-driver-content
description: The WHEA_PERSISTENCE_INFO union describes data that is used by the error record persistence interface for storing an error record.
old-location: whea\whea_persistence_info.htm
old-project: whea
ms.assetid: ab429d1b-0b4d-4897-b5f0-73113d16758e
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WHEA_PERSISTENCE_INFO, WHEA_PERSISTENCE_INFO, *PWHEA_PERSISTENCE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WHEA_PERSISTENCE_INFO
req.alt-loc: ntddk.h
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
req.iface: 
---

# WHEA_PERSISTENCE_INFO structure



## -description
<p>The WHEA_PERSISTENCE_INFO union describes data that is used by the error record persistence interface for storing an error record.</p>


## -syntax

````
typedef union _WHEA_PERSISTENCE_INFO {
  struct {
    ULONGLONG Signature  :16;
    ULONGLONG Length  :24;
    ULONGLONG Identifier  :16;
    ULONGLONG Attributes  :2;
    ULONGLONG DoNotLog  :1;
    ULONGLONG Reserved  :5;
  };
  ULONGLONG AsULONGLONG;
} WHEA_PERSISTENCE_INFO, *PWHEA_PERSISTENCE_INFO;
````


## -struct-fields
<dl>

### -field Signature

<dd>
<p>The signature of the error record when it is stored in the platform's persistent data storage. This member contains the value 'RE'.</p>
</dd>

### -field Length

<dd>
<p>The length, in bytes, of the error record when it is stored in the platform's persistent data storage.</p>
</dd>

### -field Identifier

<dd>
<p>An identifier that uniquely identifies the error record when it is stored in the platform's persistent data storage. The data type for this identifier is WHEA_ERROR_RECORD_ID.</p>
</dd>

### -field Attributes

<dd>
<p>Attribute flags that describe the error record. No attributes are currently defined.</p>
</dd>

### -field DoNotLog

<dd>
<p>A single bit that indicates that WHEA should not log an entry in the system event log for the error record.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved for system use. This member must be zero.</p>
</dd>

### -field AsULONGLONG

<dd>
<p>A ULONGLONG representation of the contents of the WHEA_PERSISTENCE_INFO union.</p>
</dd>
</dl>

## -remarks
<p>A WHEA_PERSISTENCE_INFO union is contained within the <a href="..\ntddk\ns-ntddk--whea-error-record-header.md">WHEA_ERROR_RECORD_HEADER</a> structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\ns-ntddk--whea-error-record-header.md">WHEA_ERROR_RECORD_HEADER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_PERSISTENCE_INFO union%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
