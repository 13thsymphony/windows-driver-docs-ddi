---
UID: NS.mountdev._MOUNTDEV_SUGGESTED_LINK_NAME
title: MOUNTDEV_SUGGESTED_LINK_NAME
author: windows-driver-content
description: Mount manager clients that are able to keep track of their drive letters use this structure to request that the mount manager assign them a particular link name.
old-location: storage\mountdev_suggested_link_name.htm
old-project: storage
ms.assetid: 5c6e3337-8071-486a-826a-ade722eb8449
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: MOUNTDEV_SUGGESTED_LINK_NAME, MOUNTDEV_SUGGESTED_LINK_NAME, *PMOUNTDEV_SUGGESTED_LINK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mountdev.h
req.include-header: Mountmgr.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MOUNTDEV_SUGGESTED_LINK_NAME
req.alt-loc: mountdev.h
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

# MOUNTDEV_SUGGESTED_LINK_NAME structure



## -description
<p>Mount manager clients that are able to keep track of their drive letters use this structure to request that the mount manager assign them a particular link name. </p>


## -syntax

````
typedef struct _MOUNTDEV_SUGGESTED_LINK_NAME {
  BOOLEAN UseOnlyIfThereAreNoOtherLinks;
  USHORT  NameLength;
  WCHAR   Name[1];
} MOUNTDEV_SUGGESTED_LINK_NAME, *PMOUNTDEV_SUGGESTED_LINK_NAME;
````


## -struct-fields
<dl>

### -field <b>UseOnlyIfThereAreNoOtherLinks</b>

<dd>
<p>Indicates that the mount manager should use the suggested link name only if there are no other persistent links assigned to the client. </p>
</dd>

### -field <b>NameLength</b>

<dd>
<p>Contains the length of the suggested name. </p>
</dd>

### -field <b>Name</b>

<dd>
<p>Contains a variable-sized array of wide characters that holds the name of the suggested link in wide characters. Drive letter names must include the full path of the symbolic link in object namespace and must have the traditional Microsoft MS-DOS syntax. For instance, drive letter "D" must be represented in this manner: "\DosDevices\D:". The alternative symbolic link path of "\??\D:" may not be used, nor may abbreviations of the symbolic link such as "D:". </p>
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
<dt>Mountdev.h (include Mountmgr.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\mountdev\ni-mountdev-ioctl-mountdev-query-suggested-link-name.md">IOCTL_MOUNTDEV_QUERY_SUGGESTED_LINK_NAME</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MOUNTDEV_SUGGESTED_LINK_NAME structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
