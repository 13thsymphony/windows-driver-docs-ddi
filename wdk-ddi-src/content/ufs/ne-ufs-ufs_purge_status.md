---
UID: NE.ufs.UFS_PURGE_STATUS
title: UFS_PURGE_STATUS
author: windows-driver-content
description: Specifies the current status of a purge operation.
old-location: storage\ufs_purge_status.htm
old-project: storage
ms.assetid: 9BC978A9-FA5E-4A1E-9775-1DC9C270F5DC
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: UFS_PURGE_STATUS, UFS_PURGE_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ufs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UFS_PURGE_STATUS
req.alt-loc: Ufs.h
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
req.product: Windows 10 or later.
---

# UFS_PURGE_STATUS enumeration



## -description
Specifies the current status of a purge operation.



## -syntax

````
typedef enum _UFS_PURGE_STATUS { 
  UFS_PurgeStatusIdle           = 0,
  UFS_PurgeStatusInProgress     = 1,
  UFS_PurgeStatusInterrupted    = 2,
  UFS_PurgeStatusSuccess        = 3,
  UFS_PurgeStatusQueueNotEmpty  = 4,
  UFS_PurgeStatusFailure        = 5
} UFS_PURGE_STATUS;
````


## -enum-fields

### -field UFS_PurgeStatusIdle

The status of the purge operation has already been read but was not returned.


### -field UFS_PurgeStatusInProgress

The purge operation is currently in progress.


### -field UFS_PurgeStatusInterrupted

The current purge operation was interrupted.


### -field UFS_PurgeStatusSuccess

The current purge operation was successful.


### -field UFS_PurgeStatusQueueNotEmpty

The current purge operation failed due to the logical queue being not empty.


### -field UFS_PurgeStatusFailure

The current purge operation failed.


## -remarks
When the <b>UFS_PURGE_STATUS</b> is equal to
the values 2, 3, 4, or 5, the
<b>UFS_PURGE_STATUS</b> is automatically
cleared to <b>UFS_PurgeStatusIdle</b> the first time
that it is read.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ufs.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ufs\ne-ufs-ufs_attributes_descriptor.md">UFS_ATTRIBUTES_DESCRIPTOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20UFS_PURGE_STATUS enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

