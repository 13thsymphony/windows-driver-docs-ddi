---
UID: NS.UFS.UFS_INTERCONNECT_DESCRIPTOR
title: UFS_INTERCONNECT_DESCRIPTOR
author: windows-driver-content
description: UFS_INTERCONNECT_DESCRIPTOR contains the MIPI M-PHY® specification version number and the MIPI 6338 UniPro℠ specification version number.
old-location: storage\ufs_interconnect_descriptor.htm
old-project: storage
ms.assetid: 6C6EAA96-40E9-467F-903B-AE44CE5B77CF
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: UFS_INTERCONNECT_DESCRIPTOR, *PUFS_INTERCONNECT_DESCRIPTOR, PUFS_INTERCONNECT_DESCRIPTOR, UFS_INTERCONNECT_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ufs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UFS_INTERCONNECT_DESCRIPTOR
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

# UFS_INTERCONNECT_DESCRIPTOR structure



## -description
<b>UFS_INTERCONNECT_DESCRIPTOR</b> contains the MIPI M-PHY® specification version number and the MIPI
6338 UniPro℠ specification version number.



## -syntax

````
typedef struct _UFS_INTERCONNECT_DESCRIPTOR {
  UCHAR bLength;
  UCHAR bDescriptorIDN;
  UCHAR bcdUniproVersion[2];
  UCHAR bcdMphyVersion[2];
} UFS_INTERCONNECT_DESCRIPTOR, *PUFS_INTERCONNECT_DESCRIPTOR;
````


## -struct-fields

### -field bLength

Specifies the length, in bytes, of this descriptor.


### -field bDescriptorIDN

Specifies the type of the descriptor. This descriptor will have a value of <b>UFS_DESC_INTERCONNECT_IDN</b>.


### -field bcdUniproVersion

Specifies the MIPI UniPro℠ version number in Binary Coded Decimal (BCD) format.


### -field bcdMphyVersion

Specifies the MIPI M-PHY® version number in BCD format.


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
<dt>Ufs.h</dt>
</dl>
</td>
</tr>
</table>