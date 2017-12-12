---
UID: NS.KSI.PKSCLOCKINSTANCE
title: PKSCLOCKINSTANCE
author: windows-driver-content
description: .
old-location: stream\ksclockinstance.htm
old-project: stream
ms.assetid: DC8A7CE9-7FDE-4FC9-8C71-3F3368E7E5C1
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSCLOCKINSTANCE, KSCLOCKINSTANCE, *PKSCLOCKINSTANCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCLOCKINSTANCE
req.alt-loc: Ksi.h
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

# PKSCLOCKINSTANCE structure



## -description




## -syntax

````
typedef struct {
  KSOBJECT_HEADER  Header;
  PKISDEFAULTCLOCK DefaultClock;
  ULONG            Reserved;
} KSCLOCKINSTANCE, *PKSCLOCKINSTANCE;
````


## -struct-fields

### -field Header


### -field DefaultClock


### -field Reserved


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ksi.h</dt>
</dl>
</td>
</tr>
</table>