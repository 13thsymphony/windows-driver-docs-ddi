---
UID: NE:prdrvcom.tagSHIMOPTS
title: tagSHIMOPTS
author: windows-driver-content
description: .
old-location: print\shimopts.htm
old-project: print
ms.assetid: 7A00F51A-E8EB-4D8F-B130-08834BF741C6
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: tagSHIMOPTS, SHIMOPTS, *PSHIMOPTS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: prdrvcom.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SHIMOPTS
req.alt-loc: Prdrvcom.h
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
req.typenames: SHIMOPTS, *PSHIMOPTS
req.product: Windows 10 or later.
---

# tagSHIMOPTS enumeration



## -description




## -syntax

````
typedef enum tagSHIMOPTS { 
  PTSHIM_DEFAULT     = 0,
  PTSHIM_NOSNAPSHOT  = 0x1
} SHIMOPTS, *PSHIMOPTS;
````


## -enum-fields

### -field PTSHIM_DEFAULT


### -field PTSHIM_NOSNAPSHOT


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Prdrvcom.h</dt>
</dl>
</td>
</tr>
</table>