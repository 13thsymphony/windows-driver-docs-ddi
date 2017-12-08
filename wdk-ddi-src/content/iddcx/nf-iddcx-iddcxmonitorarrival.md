---
UID: NF.iddcx.IddCxMonitorArrival
title: IddCxMonitorArrival function
author: windows-driver-content
description: An OS callback function the driver calls to report a monitor arrival on the WDDM graphics adapter.
old-location: display\iddcxmonitorarrival.htm
old-project: display
ms.assetid: e73a8111-9e54-4040-a38a-441948e10212
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: IddCxMonitorArrival
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IddCxMonitorArrival
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
---

# IddCxMonitorArrival function



## -description


                An OS callback function the driver calls to report a monitor arrival on the WDDM graphics adapter


## -syntax

````
NTSTATUS IddCxMonitorArrival(
  _In_  IDDCX_MONITOR             AdapterObject,
  _Out_ IDARG_OUT_MONITORARRIVAL* pOutArgs
);
````


## -parameters

### -param AdapterObject [in]

The adapter object that is hosting the newly arrived monitor

### -param pOutArgs [out]

Output arguments to the function

## -returns

(NTSTATUS) The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.
                    

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
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
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
_Must_inspect_result_
</td>
</tr>
</table>