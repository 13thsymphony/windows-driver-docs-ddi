---
UID: NF:hbaapi.HBA_SendRPS
title: HBA_SendRPS function
author: windows-driver-content
description: The HBA_SendRPS routine sends a read port status block (RPS) request to the indicated agent port or domain controller.
old-location: storage\hba_sendrps.htm
old-project: storage
ms.assetid: 6a79896a-0591-40dd-8e2d-6e3796556564
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HBA_SendRPS, HBA_SendRPS routine [Storage Devices], fibreHBA_rtns_753d25be-cb77-4e65-ab1b-1f2b77d65ec8.xml, hbaapi/HBA_SendRPS, storage.hba_sendrps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Hbaapi.dll
api_name:
-	HBA_SendRPS
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---


# HBA_SendRPS function
The <b>HBA_SendRPS</b> routine sends a read port status block (RPS) request to the indicated agent port or domain controller.

## Syntax

````
HBA_STATUS HBA_API HBA_SendRPS(
  _In_    HBA_HANDLE Handle,
  _In_    HBA_WWN    hbaPortWWN,
  _In_    HBA_WWN    agent_wwn,
  _In_    HBA_UINT32 agent_domain,
  _In_    HBA_WWN    object_wwn,
  _In_    HBA_UINT32 object_port_number,
  _Out_   void       *pRspBuffer,
  _Inout_ HBA_UINT32 *RspBufferSize
);
````

## Parameters

`Handle`

Contains a value returned by the routine <a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a> that identifies the local HBA through which the request is sent.

`HbaPortWWN`

TBD

`Agent_wwn`

TBD

`Agent_domain`

TBD

`Object_wwn`

TBD

`Object_port_number`

TBD

`pRspBuffer`

Pointer to a buffer that receives the results of the RPS request, if the request succeeds. If the destination port or domain controller rejects the request, this buffer holds the link service reject (LS_RJT) payload data. If the amount of returned data exceeds the buffer size specified in <i>RspBufferSize</i>, the data is truncated to the buffer size<i>. </i>The payload data is in big-endian format (higher order bytes are in lower addresses).

`pRspBufferSize`

TBD


## Return Value

The <b>HBA_SendRPS</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. In particular, <b>HBA_SendRPS</b> returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_OK</b></dt>
</dl>
</td>
<td width="60%">
Returned if the complete payload of a reply to the RPS request was successfully retrieved. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ILLEGAL_WWN</b></dt>
</dl>
</td>
<td width="60%">
Returned if the HBA referenced by <i>handle</i> does not contain a port with a name that matches <i>hbaPortWWN</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR_ELS_REJECT</b></dt>
</dl>
</td>
<td width="60%">
Returned if the destination port referenced by <i>agent_wwn </i>or the domain controller referenced by <i>agent_domain </i>rejected the request node identification information data (RNID) that identifies the source HBA. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HBA_STATUS_ERROR</b></dt>
</dl>
</td>
<td width="60%">
Returned if an unspecified error occurred that prevented the execution of the RPS request. 

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | hbaapi.h (include Hbaapi.h) |
| **Library** | Hbaapi.lib |
| **DLL** | Hbaapi.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>