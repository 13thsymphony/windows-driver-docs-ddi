---
UID: NS.IDDCX.IDDCX_OPM_GET_INFO_PARAMETERS
title: IDDCX_OPM_GET_INFO_PARAMETERS
author: windows-driver-content
description: Gives the parameters for the information request.
old-location: display\iddcx_opm_get_info_parameters.htm
old-project: display
ms.assetid: d36a0545-22cf-4980-aa1a-d3b9dd7f9871
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: IDDCX_OPM_GET_INFO_PARAMETERS,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDDCX_OPM_GET_INFO_PARAMETERS
req.alt-loc: iddcx.h
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

# IDDCX_OPM_GET_INFO_PARAMETERS structure



## -description

                 Gives the parameters for the information request.



## -syntax

````
typedef struct IDDCX_OPM_GET_INFO_PARAMETERS {
  UINT                    Size;
  OPM_GET_INFO_PARAMETERS GetInfoParameters;
} IDDCX_OPM_GET_INFO_PARAMETERS, *IDDCX_OPM_GET_INFO_PARAMETERS;
````


## -struct-fields

### -field Size


                     Total size of the structure.
                 


### -field GetInfoParameters


                     Parameters for the get information request.
                 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>