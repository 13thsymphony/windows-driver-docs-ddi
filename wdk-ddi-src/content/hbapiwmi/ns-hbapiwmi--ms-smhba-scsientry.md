---
UID: NS.hbapiwmi._MS_SMHBA_SCSIENTRY
title: MS_SMHBA_SCSIENTRY
author: windows-driver-content
description: The MS_SMHBA_SCSIENTRY structure is used to report target LUN mapping information.
old-location: storage\ms_smhba_scsientry.htm
old-project: storage
ms.assetid: 38779458-a561-4048-86d8-905e4e50095f
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: MS_SMHBA_SCSIENTRY, MS_SMHBA_SCSIENTRY, *PMS_SMHBA_SCSIENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MS_SMHBA_SCSIENTRY
req.alt-loc: hbapiwmi.h
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
req.iface: 
---

# MS_SMHBA_SCSIENTRY structure



## -description
<p>The MS_SMHBA_SCSIENTRY structure is used to report target LUN mapping information.</p>


## -syntax

````
typedef struct _MS_SMHBA_SCSIENTRY {
  MS_SMHBA_PORTLUN PortLun;
  UCHAR            LUID[256];
  HBAScsiID        ScsiId;
} MS_SMHBA_SCSIENTRY, *PMS_SMHBA_SCSIENTRY;
````


## -struct-fields
<dl>

### -field PortLun

<dd>
<p>An array of MS_SMHBA_PORTLUN entries.</p>
</dd>

### -field LUID

<dd>
<p>The logical unit descriptor for the device that the operating system derives from SCSI inquiry data.</p>
</dd>

### -field ScsiId

<dd>
<p>A structure of type HBAScsiID that contains information that uniquely identifies a logical unit to the operating system.</p>
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
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>