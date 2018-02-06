---
UID: NF:hbaapi.HBA_SendCTPassThruV2
title: HBA_SendCTPassThruV2 function
author: windows-driver-content
description: The HBA_SendCTPassThruV2 routine sends a common transport (CT) pass-through command through the indicated port.
old-location: storage\hba_sendctpassthruv2.htm
old-project: storage
ms.assetid: 95526c2d-19bf-4f4a-abfa-e5be73c1a6a5
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: hbaapi/HBA_SendCTPassThruV2, HBA_SendCTPassThruV2 routine [Storage Devices], storage.hba_sendctpassthruv2, fibreHBA_rtns_8ed894f5-3f6c-4b71-a149-8e5624643aa0.xml, HBA_SendCTPassThruV2
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
-	HBA_SendCTPassThruV2
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---


# HBA_SendCTPassThruV2 function
The <b>HBA_SendCTPassThruV2</b> routine sends a common transport (CT) pass-through command through the indicated port.

## Syntax

````
HBA_STATUS HBA_API HBA_SendCTPassThruV2(
  _In_    HBA_HANDLE HbaHandle,
  _In_    HBA_WWN    HbaPortWWN,
  _In_    void       *pReqBuffer,
  _In_    HBA_UINT32 ReqBufferSize,
  _Out_   void       *pRspBuffer,
  _Inout_ HBA_UINT32 *RspBufferSize
);
````

## Parameters

`Handle`

TBD

`HbaPortWWN`

Contains the worldwide name (WWN) of the port from which to issue the command. For a definition of worldwide names, see the T11 committee's specification for <i>Fibre Channel HBA API</i>.

`pReqBuffer`

Pointer to a buffer that contains the full frame of the common transport command in big-endian format.

`ReqBufferSize`

Indicates the size of the buffer pointed to by <i>pReqBuffer</i>:

`pRspBuffer`

Pointer to a buffer that contains the payload data from the reply to the common transport command in big-endian (wire) format.

`pRspBufferSize`

TBD


## Return Value

The <b>HBA_SendCTPassThruV2</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA. If the HBA successfully delivers the command to the destination service, and the service executes the command and successfully returns the results, the HBA_SendCTPassThru routine returns a value of HBA_STATUS_OK. If the command does not succeed, this routine returns an appropriate error code of type HBA_STATUS.

## Remarks

The <b>HBA_SendCTPassThruV2</b> library routine is identical to the <a href="..\hbaapi\nf-hbaapi-hba_sendctpassthru.md">HBA_SendCTPassThru</a> routine, except that <b>HBA_SendCTPassThruV2</b> allows the caller to specify the port through which the CT command will be issued. 

The <b>HBA_SendCTPassThruV2</b> library routine serves a purpose very similar to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565409">SendCTPassThru</a> WMI method. 

A CT command can request services that distribute encryption keys, IP addresses, time stamps, names, aliases, fabric configuration, and security policies. For a complete list of the service types that can be specified in a CT command, see the <i>Fibre Channel Generic Services - 4 (FC-GS-4)</i> specification published by the ANSI committee.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | hbaapi.h (include Hbaapi.h) |
| **Library** | Hbaapi.lib |
| **DLL** | Hbaapi.dll |

## See Also

<a href="..\hbaapi\nf-hbaapi-hba_sendctpassthru.md">HBA_SendCTPassThru</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>

<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565409">SendCTPassThru</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_SendCTPassThruV2 routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>