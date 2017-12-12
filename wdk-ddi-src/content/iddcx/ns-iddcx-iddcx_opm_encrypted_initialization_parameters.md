---
UID: NS.IDDCX.IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS
title: IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS
author: windows-driver-content
description: Gives information about the OPM encrypted initialization parameters.
old-location: display\iddcx_opm_encrypted_initialization_parameters.htm
old-project: display
ms.assetid: d1df3fc1-2d23-4e90-b663-6322ba4e1eff
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS,
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
req.alt-api: IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS
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

# IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS structure



## -description
Gives information about the OPM encrypted initialization parameters.
             



## -syntax

````
typedef struct IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS {
  UINT                                    Size;
  OPM_ENCRYPTED_INITIALIZATION_PARAMETERS EncryptedParameters;
} IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS, *IDDCX_OPM_ENCRYPTED_INITIALIZATION_PARAMETERS;
````


## -struct-fields

### -field Size


                     Total size of the structure.
                 


### -field EncryptedParameters


                     Initialization parameters.
                 


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