---
UID : NF:hbaapi.HBA_GetDiscoveredPortAttributes
title : HBA_GetDiscoveredPortAttributes function
author : windows-driver-content
description : The HBA_GetDiscoveredPortAttributes routine retrieves the attributes for a specified remote fibre channel port.
old-location : storage\hba_getdiscoveredportattributes.htm
old-project : storage
ms.assetid : 64c6ed50-a4b9-4a8c-b38c-b2fcdf5ccee9
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : hbaapi/HBA_GetDiscoveredPortAttributes, storage.hba_getdiscoveredportattributes, HBA_GetDiscoveredPortAttributes, HBA_GetDiscoveredPortAttributes routine [Storage Devices], fibreHBA_rtns_3f74a187-728d-4534-8ad8-29e1a9b0add5.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : hbaapi.h
req.include-header : Hbaapi.h
req.target-type : Desktop
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
req.lib : Hbaapi.lib
req.dll : Hbaapi.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : HBA_WWNTYPE
---


# HBA_GetDiscoveredPortAttributes function
The <b>HBA_GetDiscoveredPortAttributes</b> routine retrieves the attributes for a specified remote fibre channel port.

## Syntax

````
HBA_STATUS HBA_API HBA_GetDiscoveredPortAttributes(
  _In_  HBA_HANDLE         HbaHandle,
  _In_  HBA_UINT32         PortIndex,
  _In_  HBA_UINT32         DiscoveredPortIndex,
  _Out_ HBA_PORTATTRIBUTES *HbaPortAttributes
);
````

## Parameters

`Handle`

TBD

`PortIndex`

Indicates the index of the local port of type Nx_Port through which to query the discovered remote port. For a definition of Nx_Port, see the T11 committee's <i>Fibre Channel HBA API</i> specification.

`DiscoveredPortIndex`

Indicates the index of the remote port to query.

`PortAttributes`

TBD


## Return Value

The <b>HBA_GetDiscoveredPortAttributes</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA.

## Remarks

The <b>HBA_GetDiscoveredPortAttributes</b> library routine corresponds to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553925">GetDiscoveredPortAttributes</a> WMI method.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbaapi.h (include Hbaapi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\hbaapi\ns-hbaapi-hba_portattributes.md">HBA_PortAttributes</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553925">GetDiscoveredPortAttributes</a>

<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetDiscoveredPortAttributes routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>