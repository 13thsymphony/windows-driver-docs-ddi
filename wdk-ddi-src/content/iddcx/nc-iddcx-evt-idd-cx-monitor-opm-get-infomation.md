---
UID: NC.iddcx.EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION
title: EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION
author: windows-driver-content
description: EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION is called by the OS to get OPM information.
old-location: display\evt_idd_cx_monitor_opm_get_infomation.htm
old-project: display
ms.assetid: b616a105-3c4b-42b7-8352-a1f35479572e
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: WcsTranslateColors
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFN_IDD_CX_MONITOR_OPM_GET_INFOMATION
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
req.irql: _requires_same_
req.iface: 
---

# EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION callback



## -description
<p><b>EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION</b> is called by the OS to get OPM information.</p>


## -prototype

````
EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION EvtIddCxMonitorOpmGetInfomation;

NTSTATUS EvtIddCxMonitorOpmGetInfomation(
  _In_        IDDCX_OPMCTX                  OpmCxtObject,
  _In_  const IDARG_IN_OPM_GET_INFOMATION*  pInArgs,
  _Out_       IDARG_OUT_OPM_GET_INFOMATION* pOutArgs
)
{ ... }

typedef EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION PFN_IDD_CX_MONITOR_OPM_GET_INFOMATION;
````


## -parameters
<dl>

### -param OpmCxtObject [in]

<dd>
<p>
                    
                The object for the OPM context that information will be gotten from.</p>
</dd>

### -param pInArgs [in]

<dd>
<p>
                    
                Input arguments used by <b>EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION</b>.</p>
</dd>

### -param pOutArgs [out]

<dd>
<p>
                    
                Output arguments returned by <b>EVT_IDD_CX_MONITOR_OPM_GET_INFOMATION</b>.</p>
</dd>
</dl>

## -returns
<p>
(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 
                    </p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
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
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>_requires_same_</p>
</td>
</tr>
</table>