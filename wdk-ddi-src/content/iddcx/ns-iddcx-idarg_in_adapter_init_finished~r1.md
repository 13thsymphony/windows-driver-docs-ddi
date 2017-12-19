---
UID: NS.IDDCX.IDARG_IN_ADAPTER_INIT_FINISHED~R1
title: IDARG_IN_ADAPTER_INIT_FINISHED
author: windows-driver-content
description: Gives the status of the adapter initialization.
old-location: display\idarg_in_adapter_init_finished.htm
old-project: display
ms.assetid: 7ff07613-7c40-4310-856a-a44dc97c7f20
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: IDARG_IN_ADAPTER_INIT_FINISHED,
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
req.alt-api: IDARG_IN_ADAPTER_INIT_FINISHED
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

# IDARG_IN_ADAPTER_INIT_FINISHED structure



## -description

                 Gives the status of the adapter initialization.



## -syntax

````
typedef struct IDARG_IN_ADAPTER_INIT_FINISHED {
  NTSTATUS AdapterInitStatus;
} IDARG_IN_ADAPTER_INIT_FINISHED, *IDARG_IN_ADAPTER_INIT_FINISHED;
````


## -struct-fields

### -field AdapterInitStatus


                     The initialization status of the adapter.
                 


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