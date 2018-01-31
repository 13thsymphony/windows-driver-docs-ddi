---
UID : NF:ks.KSEVENT_ENTRY_IRP_STORAGE
title : KSEVENT_ENTRY_IRP_STORAGE macro
author : windows-driver-content
description : This macro retrieves a pointer to the KSEVENT_ENTRY structure stored in Irp.
old-location : stream\ksevent_entry_irp_storage.htm
old-project : stream
ms.assetid : 9d5d30a5-4c87-4651-89e6-0fe4b02e7ea0
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : stream.ksevent_entry_irp_storage, KSEVENT_ENTRY_IRP_STORAGE, KSEVENT_ENTRY_IRP_STORAGE macro [Streaming Media Devices], ks/KSEVENT_ENTRY_IRP_STORAGE, ksfunc_174dded2-4521-4d4a-b7ab-13401da80e5b.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ks.h
req.include-header : Ks.h
req.target-type : Windows
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
req.lib : ks.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : 
---


# KSEVENT_ENTRY_IRP_STORAGE function
This macro retrieves a pointer to the <a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a> structure stored in <i>Irp</i>. This information is initialized only for enable requests; it is not initialized for basic support requests. If the event enable is to be handled asynchronously, this storage location must be maintained intact.

## Syntax

````
 KSEVENT_ENTRY_IRP_STORAGE(
    Irp
);
````

## Parameters

`Irp`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |