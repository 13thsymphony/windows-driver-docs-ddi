---
UID: NF.ntifs.FsRtlIsDaxVolume
title: FsRtlIsDaxVolume function
author: windows-driver-content
description: This routine queries if the specified file is on a direct access (DAX) volume.
old-location: ifsk\fsrtlisdaxvolume.htm
old-project: ifsk
ms.assetid: FFCD2329-FD6A-48AE-8E9D-56AA7D79B174
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FsRtlIsDaxVolume
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlIsDaxVolume
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

# FsRtlIsDaxVolume function



## -description
This routine queries if the specified file is on a  direct access (DAX) volume.


## -syntax

````
BOOLEAN FsRtlIsDaxVolume(
  _In_ PFILE_OBJECT FileObject
);
````


## -parameters

### -param FileObject [in]

A file object for a file, on the volume which is being queried.

## -returns
Returns <b>true</b> if the file is on a DAX volume; otherwise, <b>false</b>.

## -remarks
In DAX volumes,  user files
    are mapped directly to the persistent memory device.  Files are
    then accessed using the memory bus, to help boost system performance.

## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10, version 1607
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
<dt>Ntifs.h</dt>
</dl>
</td>
</tr>
</table>