---
UID: NS.bdatypes._BDA_TABLE_SECTION
title: BDA_TABLE_SECTION
author: windows-driver-content
description: The BDA_TABLE_SECTION structure describes a table section.
old-location: stream\bda_table_section.htm
old-project: stream
ms.assetid: f7669c36-6bf0-477e-8466-46a3da015cf3
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: BDA_TABLE_SECTION, BDA_TABLE_SECTION, *PBDA_TABLE_SECTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
req.include-header: Bdatypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BDA_TABLE_SECTION
req.alt-loc: bdatypes.h
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

# BDA_TABLE_SECTION structure



## -description
<p>The BDA_TABLE_SECTION structure describes a table section. </p>


## -syntax

````
typedef struct _BDA_TABLE_SECTION {
  ULONG ulPrimarySectionId;
  ULONG ulSecondarySectionId;
  ULONG ulcbSectionLength;
  ULONG argbSectionData[MIN_DIMENSION];
} BDA_TABLE_SECTION, *PBDA_TABLE_SECTION;
````


## -struct-fields
<dl>

### -field <b>ulPrimarySectionId</b>

<dd>
<p>Identifier of the primary table section. </p>
</dd>

### -field <b>ulSecondarySectionId</b>

<dd>
<p>Identifier of the secondary table section. </p>
</dd>

### -field <b>ulcbSectionLength</b>

<dd>
<p>Size, in bytes, of the <b>argbSectionData</b> array. </p>
</dd>

### -field <b>argbSectionData</b>

<dd>
<p>Array of table section data.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Bdatypes.h (include Bdatypes.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566560">KSPROPSETID_BdaTableSection</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BDA_TABLE_SECTION structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
