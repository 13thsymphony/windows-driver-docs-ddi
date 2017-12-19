---
UID: NE.rilapitypes.RILREQUESTGEOLOCATIONDATAPARAMMASK
title: RILREQUESTGEOLOCATIONDATAPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrequestgeolocationdataparammask_2.htm
old-project: NetVista
ms.assetid: b81cbf26-7164-4082-a505-2a849ec3d1ea
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILREQUESTGEOLOCATIONDATAPARAMMASK, RILREQUESTGEOLOCATIONDATAPARAMMASK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILREQUESTGEOLOCATIONDATAPARAMMASK
req.alt-loc: rilapitypes.h
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
req.product: Windows 10 or later.
---

# RILREQUESTGEOLOCATIONDATAPARAMMASK enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILREQUESTGEOLOCATIONDATAPARAMMASK { 
  RIL_PARAM_REQUESTGEOLOCATIONDATA_SIZE,
  RIL_PARAM_REQUESTGEOLOCATIONDATA_EXECUTOR,
  RIL_PARAM_REQUESTGEOLOCATIONDATA_MASK,
  RIL_PARAM_REQUESTGEOLOCATIONDATA_REQUESTACCCURACY,
  RIL_PARAM_REQUESTGEOLOCATIONDATA_REQUESTINFORMATION,
  RIL_PARAM_REQUESTGEOLOCATIONDATA_ALL
} RILREQUESTGEOLOCATIONDATAPARAMMASK;
````


## -enum-fields

### -field RIL_PARAM_REQUESTGEOLOCATIONDATA_SIZE


### -field RIL_PARAM_REQUESTGEOLOCATIONDATA_EXECUTOR


### -field RIL_PARAM_REQUESTGEOLOCATIONDATA_MASK


### -field RIL_PARAM_REQUESTGEOLOCATIONDATA_REQUESTACCCURACY


### -field RIL_PARAM_REQUESTGEOLOCATIONDATA_REQUESTINFORMATION


### -field RIL_PARAM_REQUESTGEOLOCATIONDATA_ALL


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>