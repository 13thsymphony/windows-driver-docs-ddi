---
UID: NE:wdm._DIRECTORY_NOTIFY_INFORMATION_CLASS
title: _DIRECTORY_NOTIFY_INFORMATION_CLASS
author: windows-driver-content
description: A value that specifies which structure to use to query or set information for a files in a directory.
old-location: ifsk\_directory_notify_information_class.htm
old-project: ifsk
ms.assetid: 77c2515b-f20a-47ac-9564-9eab009cf625
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _DIRECTORY_NOTIFY_INFORMATION_CLASS, *PDIRECTORY_NOTIFY_INFORMATION_CLASS, DIRECTORY_NOTIFY_INFORMATION_CLASS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DIRECTORY_NOTIFY_INFORMATION_CLASS
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (See Remarks section)
req.typenames: *PDIRECTORY_NOTIFY_INFORMATION_CLASS, DIRECTORY_NOTIFY_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# _DIRECTORY_NOTIFY_INFORMATION_CLASS enumeration



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

A value that specifies which structure to use to query or set information for a files in a directory.



## -syntax

````
typedef enum _DIRECTORY_NOTIFY_INFORMATION_CLASS { 
  DirectoryNotifyInformation          = 1,
  DirectoryNotifyExtendedInformation
} DIRECTORY_NOTIFY_INFORMATION_CLASS;
````


## -enum-fields

### -field DirectoryNotifyInformation

A <b>FILE_NOTIFY_INFORMATION </b>structure.


### -field DirectoryNotifyExtendedInformation

A <b>FILE_NOTIFY_EXTENDED_INFORMATION</b> structure.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10, version 1709

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h</dt>
</dl>
</td>
</tr>
</table>