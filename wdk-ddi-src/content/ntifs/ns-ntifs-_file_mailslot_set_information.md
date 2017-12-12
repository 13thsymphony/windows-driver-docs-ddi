---
UID: NS.NTIFS._FILE_MAILSLOT_SET_INFORMATION
title: _FILE_MAILSLOT_SET_INFORMATION
author: windows-driver-content
description: The FILE_MAILSLOT_SET_INFORMATION structure is used to set a value on a mailslot.
old-location: ifsk\file_mailslot_set_information.htm
old-project: ifsk
ms.assetid: 65104303-5041-45e7-bd59-bb78dde1dffd
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _FILE_MAILSLOT_SET_INFORMATION, *PFILE_MAILSLOT_SET_INFORMATION, FILE_MAILSLOT_SET_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_MAILSLOT_SET_INFORMATION
req.alt-loc: ntifs.h
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

# _FILE_MAILSLOT_SET_INFORMATION structure



## -description
The <b>FILE_MAILSLOT_SET_INFORMATION</b> structure is used to set a value on a   mailslot.



## -syntax

````
typedef struct _FILE_MAILSLOT_SET_INFORMATION {
  PLARGE_INTEGER  ReadTimeout;
} FILE_MAILSLOT_SET_INFORMATION, *PFILE_MAILSLOT_SET_INFORMATION;
````


## -struct-fields

### -field ReadTimeout


The time, in milliseconds, that a read operation can wait for a message to be written to the mailslot before a time-out occurs. A value of –1 requests that the read wait forever for a message without timing out. A value of 0 requests that the read not wait and return immediately whether a pending message is available to be read or not.



## -remarks
For more information, see <a href="base.mailslots">Mailslots</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 2000 and later versions of the Windows operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include FltKernel.h or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>