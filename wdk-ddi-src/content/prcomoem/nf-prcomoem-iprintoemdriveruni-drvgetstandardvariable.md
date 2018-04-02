---
UID: NF:prcomoem.IPrintOemDriverUni.DrvGetStandardVariable
title: IPrintOemDriverUni::DrvGetStandardVariable method
author: windows-driver-content
description: The IPrintOemDriverUni::DrvGetStandardVariable method is provided by the Unidrv driver so that rendering plug-ins can obtain the current value of Unidrv's standard variables.
old-location: print\iprintoemdriveruni_drvgetstandardvariable.htm
old-project: print
ms.assetid: d55d3130-14e7-438f-bfb5-18927466bd60
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DrvGetStandardVariable method [Print Devices], DrvGetStandardVariable method [Print Devices], IPrintOemDriverUni interface, DrvGetStandardVariable,IPrintOemDriverUni.DrvGetStandardVariable, IPrintOemDriverUni, IPrintOemDriverUni interface [Print Devices], DrvGetStandardVariable method, IPrintOemDriverUni::DrvGetStandardVariable, prcomoem/IPrintOemDriverUni::DrvGetStandardVariable, print.iprintoemdriveruni_drvgetstandardvariable, print_unidrv-pscript_rendering_001f3a93-7022-4436-8191-5cb091bc3c42.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintOemDriverUni.DrvGetStandardVariable
product:
- Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# IPrintOemDriverUni::DrvGetStandardVariable method
The <code>IPrintOemDriverUni::DrvGetStandardVariable</code> method is provided by the Unidrv driver so that rendering plug-ins can obtain the current value of Unidrv's <a href="https://msdn.microsoft.com/d3f85c0f-7387-4301-8b1e-904471aed4b0">standard variables</a>.

## Syntax

```
HRESULT DrvGetStandardVariable(
  PDEVOBJ pdevobj,
  DWORD   dwIndex,
  PVOID   pBuffer,
  DWORD   cbSize,
  PDWORD  pcbNeeded
);
```

## Parameters

`pdevobj`

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547573">DEVOBJ</a> structure.

`dwIndex`

Caller-supplied, SVI_-prefixed index into the list of Unidrv's standard variables. The SVI_-prefixed index values are defined in printoem.h.

`pBuffer`

Caller-supplied pointer to a DWORD to receive the standard variable's current value.

`cbSize`

Caller-supplied size of the buffer pointed to by <i>pBuffer</i>.

`pcbNeeded`

Caller-supplied pointer to a location to receive the minimum buffer size required to contain the requested information.


## Return Value

The method must return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not implemented.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | prcomoem.h (include Prcomoem.h) |