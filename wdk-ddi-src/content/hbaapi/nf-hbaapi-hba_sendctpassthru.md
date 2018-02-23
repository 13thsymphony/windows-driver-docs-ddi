---
UID: NF:hbaapi.HBA_SendCTPassThru
title: HBA_SendCTPassThru function
author: windows-driver-content
description: The HBA_SendCTPassThru routine sends a common transport (CT) pass-through command.
old-location: storage\hba_sendctpassthru.htm
old-project: storage
ms.assetid: adfdb968-5ba3-43af-899a-7172c9ecf46c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: HBA_SendCTPassThru, hbaapi/HBA_SendCTPassThru, HBA_SendCTPassThru routine [Storage Devices], storage.hba_sendctpassthru, fibreHBA_rtns_cae90bb3-cdb2-47fe-92b8-e2bffefa338d.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hbaapi.dll
apiname:
-	HBA_SendCTPassThru
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---


# HBA_SendCTPassThru function
The <b>HBA_SendCTPassThru</b> routine sends a common transport (CT) pass-through command.

## Syntax

````
HBA_STATUS HBA_API HBA_SendCTPassThru(
  _In_  HBA_HANDLE HbaHandle,
  _In_  void       *pReqBuffer,
  _In_  HBA_UINT32 ReqBufferSize,
  _Out_ void       *pRspBuffer,
  _In_  HBA_UINT32 RspBufferSize
);
````

## Parameters

`Handle`

TBD

`pReqBuffer`

Pointer to a buffer that contains the full frame of the common transport command in big-endian (wire) format.

`ReqBufferSize`

Indicates the size of the buffer pointed to by <i>pReqBuffer</i>:

`pRspBuffer`

Pointer to a buffer that contains the payload data from the reply to the common transport command in big-endian (wire) format.

`RspBufferSize`

Indicates the size of the buffer pointed to by <i>pRspBuffer</i>.


## Return Value

The <b>HBA_SendCTPassThru</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. If the HBA successfully delivers the command to the destination service, and the service executes the command and successfully returns the results, the HBA_SendCTPassThru routine returns a value of HBA_STATUS_OK. If the command does not succeed, this routine returns an appropriate error code of type HBA_STATUS.

## Remarks

The <b>HBA_SendCTPassThru</b> library routine serves a purpose very similar to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565409">SendCTPassThru</a> WMI method. 

A CT command can request services that distribute encryption keys, IP addresses, time stamps, names, aliases, fabric configuration, and security policies. For a complete list of the service types that can be specified in a CT command, see the <i>Fibre Channel Generic Services - 4 (FC-GS-4)</i> specification published by the ANSI committee.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | hbaapi.h (include Hbaapi.h) |
| **Library** | Hbaapi.lib |
| **DLL** | Hbaapi.dll |

## See Also

<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="..\hbaapi\nf-hbaapi-hba_sendctpassthruv2.md">HBA_SendCTPassThruV2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_SendCTPassThru routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>