---
UID: NS.IDDCX.IDARG_IN_OPM_GET_CERTIFICATE_SIZE
title: IDARG_IN_OPM_GET_CERTIFICATE_SIZE
author: windows-driver-content
description: Gives information about the OPM certificate size.
old-location: display\idarg_in_opm_get_certificate_size.htm
old-project: display
ms.assetid: 42b8bd6c-c5be-45d0-9537-13d687ca5a48
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: IDARG_IN_OPM_GET_CERTIFICATE_SIZE,
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
req.alt-api: IDARG_IN_OPM_GET_CERTIFICATE_SIZE
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

# IDARG_IN_OPM_GET_CERTIFICATE_SIZE structure



## -description
Gives information about the OPM certificate size.



## -syntax

````
typedef struct IDARG_IN_OPM_GET_CERTIFICATE_SIZE {
  OPM_VIDEO_OUTPUT_SEMANTICS CertificateType;
} IDARG_IN_OPM_GET_CERTIFICATE_SIZE, *IDARG_IN_OPM_GET_CERTIFICATE_SIZE;
````


## -struct-fields

### -field CertificateType


                     [in] Type of certificate the size request is for.
                 


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