---
UID : NF:ks.KsDispatchSpecificProperty
title : KsDispatchSpecificProperty function
author : windows-driver-content
description : The KsDispatchSpecificProperty function dispatches the property to a specific handler.
old-location : stream\ksdispatchspecificproperty.htm
old-project : stream
ms.assetid : 3ea9a473-606d-4021-89af-5f895020d054
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : stream.ksdispatchspecificproperty, KsDispatchSpecificProperty function [Streaming Media Devices], KsDispatchSpecificProperty, ks/KsDispatchSpecificProperty, ksfunc_b12751b9-b486-4b57-809b-1f3daa8a1c30.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
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
req.lib : Ks.lib
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


# KsDispatchSpecificProperty function
The <b>KsDispatchSpecificProperty</b> function dispatches the property to a specific handler. The function assumes that the caller has previously dispatched this IRP to a handler through the <b>KsPropertyHandler</b> function. 

This function can only be called at PASSIVE_LEVEL.

## Syntax

````
KSDDKAPI NTSTATUS NTAPI KsDispatchSpecificProperty(void);
````

## Parameters

`Irp`

TBD

`Handler`

TBD


## Return Value

The <b>KsDispatchSpecificProperty</b> function returns STATUS_SUCCESS if successful, or if unsuccessful it returns an error.

## Remarks

The <b>KsDispatchSpecificProperty</b> function is intended for additional processing of a property such as completing a pending operation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |

## See Also

<a href="..\ks\nf-ks-kspropertyhandler.md">KsPropertyHandler</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDispatchSpecificProperty function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>