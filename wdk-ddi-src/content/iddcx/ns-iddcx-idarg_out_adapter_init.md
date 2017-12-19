---
UID: NS.IDDCX.IDARG_OUT_ADAPTER_INIT
title: IDARG_OUT_ADAPTER_INIT
author: windows-driver-content
description: Gives information about the initialized adapter that can be used by the OS to call functions.
old-location: display\idarg_out_adapter_init.htm
old-project: display
ms.assetid: 55e4c835-88c8-403f-883c-182915aa614d
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IDARG_OUT_ADAPTER_INIT,
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
req.alt-api: IDARG_OUT_ADAPTER_INIT
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

# IDARG_OUT_ADAPTER_INIT structure



## -description
Gives information about the initialized adapter that can be used by the OS to call functions.
                 
             



## -syntax

````
typedef struct IDARG_OUT_ADAPTER_INIT {
  IDDCX_ADAPTER AdapterObject;
} IDARG_OUT_ADAPTER_INIT, *IDARG_OUT_ADAPTER_INIT;
````


## -struct-fields

### -field AdapterObject


                     [out] Handle to the adapter that the driver can use to identify it when calling OS functions.
                 


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