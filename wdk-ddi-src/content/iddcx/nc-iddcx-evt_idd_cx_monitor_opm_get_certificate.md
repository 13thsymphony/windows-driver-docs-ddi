---
UID: NC.iddcx.EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE
title: EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE
author: windows-driver-content
description: EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE is called by the OS to get an OPM certificate.
old-location: display\evt_idd_cx_monitor_opm_get_certificate.htm
old-project: display
ms.assetid: f1a3882e-7d45-4634-ae1d-fb8102716f36
ms.author: windowsdriverdev
ms.date: 12/8/2017
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
req.alt-api: PFN_IDD_CX_MONITOR_OPM_GET_CERTIFICATE
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
---

# EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE callback



## -description
<b>EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE</b> is called by the OS to get an OPM certificate.



## -prototype

````
EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE EvtIddCxMonitorOpmGetCertificate;

NTSTATUS EvtIddCxMonitorOpmGetCertificate(
  _In_       IDDCX_ADAPTER                 AdapterObject,
  _In_ const IDARG_IN_OPM_GET_CERTIFICATE* pInArgs
)
{ ... }

typedef EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE PFN_IDD_CX_MONITOR_OPM_GET_CERTIFICATE;
````


## -parameters

### -param AdapterObject [in]


                    
                The object for the adapter that the OPM certificate will be gotten for.


### -param pInArgs [in]


                    
                Input arguments used by <b>EVT_IDD_CX_MONITOR_OPM_GET_CERTIFICATE</b>.


## -returns

(NTSTATUS) If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise, an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code. 
                    


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
_requires_same_

</td>
</tr>
</table>