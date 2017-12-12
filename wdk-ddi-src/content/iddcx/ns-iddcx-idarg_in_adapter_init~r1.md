---
UID: NS.IDDCX.IDARG_IN_ADAPTER_INIT~R1
title: IDARG_IN_ADAPTER_INIT
author: windows-driver-content
description: Initializes an adapter that will be hosted on a WDF device.
old-location: display\idarg_in_adapter_init.htm
old-project: display
ms.assetid: 2db324c8-69b1-4497-b6a7-76047baeca19
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: IDARG_IN_ADAPTER_INIT,
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
req.alt-api: IDARG_IN_ADAPTER_INIT
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

# IDARG_IN_ADAPTER_INIT structure



## -description

                 Initializes an adapter that will be hosted on a WDF device.
             



## -syntax

````
typedef struct IDARG_IN_ADAPTER_INIT {
  WDFDEVICE              WdfDevice;
  IDDCX_ADAPTER_CAPS*    pCaps;
  PWDF_OBJECT_ATTRIBUTES ObjectAttributes;
} IDARG_IN_ADAPTER_INIT, *IDARG_IN_ADAPTER_INIT;
````


## -struct-fields

### -field WdfDevice


                     The WDF device that will be hosting this WDDM adapter object.
                 


### -field pCaps


                     [in] A reference  to the capabilities of the adapter.
                 


### -field ObjectAttributes


                     [in][optional] Object attributes that are used to initialize the WDF adapter object.
                 


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