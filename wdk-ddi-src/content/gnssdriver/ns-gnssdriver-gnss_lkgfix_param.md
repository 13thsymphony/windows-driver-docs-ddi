---
UID: NS.GNSSDRIVER.GNSS_LKGFIX_PARAM
title: GNSS_LKGFIX_PARAM
author: windows-driver-content
description: This structure is not used currently by the system and is not required to be implemented.
old-location: sensors\gnss_lkgfix_param.htm
old-project: sensors
ms.assetid: AE4F03D6-A3A7-40DD-9DD9-D9B8F25FD567
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_LKGFIX_PARAM, GNSS_LKGFIX_PARAM, PGNSS_LKGFIX_PARAM, *PGNSS_LKGFIX_PARAM
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GNSS_LKGFIX_PARAM
req.alt-loc: gnssdriver.h
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

# GNSS_LKGFIX_PARAM structure



## -description
This structure is not used currently by the system and is not required to be implemented.



## -syntax

````
typedef struct {
  ULONG Size;
  ULONG Version;
} GNSS_LKGFIX_PARAM, *PGNSS_LKGFIX_PARAM;
````


## -struct-fields

### -field Size

Structure size.


### -field Version

Version number.


## -remarks
No additional parameter is needed for an LKG fix. The GNSS adapter implements any aging heuristics for rejecting an LKG fix received from the GNSS driver based on the difference between the fix time and current time.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Gnssdriver.h</dt>
</dl>
</td>
</tr>
</table>