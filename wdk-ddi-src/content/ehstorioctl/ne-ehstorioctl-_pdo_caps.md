---
UID: NE.ehstorioctl._PDO_CAPS
title: _PDO_CAPS
author: windows-driver-content
description: This enumeration describes the capabilities of Physical Device Objects (PDOs).
old-location: storage\pdo_caps.htm
old-project: storage
ms.assetid: 78b6f3c7-bb42-4e93-8128-28b6f8e11dda
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _PDO_CAPS, PDO_CAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PDO_CAPS
req.alt-loc: EhStorIoctl.h
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

# _PDO_CAPS enumeration



## -description
This enumeration describes the capabilities of Physical Device Objects (PDOs).



## -syntax

````
typedef enum _PDO_CAPS { 
  PDO_CAPABILITY_UNDEFINED     = 0,
  PDO_CAPABILITY_INC512_SET    = 1,
  PDO_CAPABILITY_INC512_CLEAR  = 2
} PDO_CAPS;
````


## -enum-fields

### -field PDO_CAPABILITY_UNDEFINED

Command data block size granularity is undefined.


### -field PDO_CAPABILITY_INC512_SET

Command data block size granularity of 512 bytes is supported.


### -field PDO_CAPABILITY_INC512_CLEAR

Command data block size granularity of 1 byte is supported.


## -remarks
A silo must support either PDO_CAPABILITY_INC512_SET or PDO_CAPABILITY_INC512_CLEAR. It may also indicate that both values are supported by returning a logical OR of these two bits.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>EhStorIoctl.h (include EhStorIoctl.h)</dt>
</dl>
</td>
</tr>
</table>