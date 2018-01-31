---
UID : NF:portcls.IServiceSink.RequestService
title : IServiceSink::RequestService method
author : windows-driver-content
description : The RequestService method is called to forward a service request to an IServiceSink object.
old-location : audio\iservicesink_requestservice.htm
old-project : audio
ms.assetid : c5035dee-3523-4b0d-9baa-e30720115499
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : IServiceSink interface [Audio Devices], RequestService method, RequestService method [Audio Devices], IServiceSink interface, audio.iservicesink_requestservice, RequestService method [Audio Devices], IServiceSink, portcls/IServiceSink::RequestService, RequestService, audmp-routines_c59de1c6-446e-489b-ba96-c2b24f74576a.xml, IServiceSink::RequestService
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : portcls.h
req.include-header : Portcls.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : portcls.h
req.dll : 
req.irql : DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# RequestService method
The <code>RequestService</code> method is called to forward a service request to an <b>IServiceSink</b> object.

## Syntax

````
VOID RequestService(
    None
);
````

## Parameters

This function has no parameters.

## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | portcls.h (include Portcls.h) |
| **Library** |  |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** |  |