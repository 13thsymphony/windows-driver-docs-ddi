---
UID: NS.iddcx.IDARG_OUT_OPM_GET_CERTIFICATE_SIZE
title: IDARG_OUT_OPM_GET_CERTIFICATE_SIZE
author: windows-driver-content
description: Gives information about the OPM certificate size.
old-location: display\idarg_out_opm_get_certificate_size.htm
old-project: display
ms.assetid: 983e4bda-160d-4a3d-9a50-0ceabc70114f
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: IDARG_OUT_OPM_GET_CERTIFICATE_SIZE,
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
req.alt-api: IDARG_OUT_OPM_GET_CERTIFICATE_SIZE
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
req.irql: _Must_inspect_result_
req.iface: 
---

# IDARG_OUT_OPM_GET_CERTIFICATE_SIZE structure



## -description
<p>
                 Gives information about the OPM certificate size.</p>


## -syntax

````
typedef struct IDARG_OUT_OPM_GET_CERTIFICATE_SIZE {
  UINT CertificateSize;
} IDARG_OUT_OPM_GET_CERTIFICATE_SIZE, *IDARG_OUT_OPM_GET_CERTIFICATE_SIZE;
````


## -struct-fields
<dl>

### -field <b>CertificateSize</b>

<dd>
<p>
                     [out] Size of the OPM certificate.
                 </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>