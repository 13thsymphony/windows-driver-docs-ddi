---
UID : NF:ndis.NdisCloseConfiguration
title : NdisCloseConfiguration function
author : windows-driver-content
description : The NdisCloseConfiguration function releases the handle to the registry key that was returned by the NdisOpenConfigurationEx, NdisOpenConfigurationKeyByIndex, or NdisOpenConfigurationKeyByName function.
old-location : netvista\ndiscloseconfiguration.htm
old-project : netvista
ms.assetid : 2d68f7dd-3954-4b3b-8673-1da63e1a1edc
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NdisCloseConfiguration function [Network Drivers Starting with Windows Vista], ndis/NdisCloseConfiguration, NdisCloseConfiguration, netvista.ndiscloseconfiguration, ndis_configuration_ref_eb02fa4e-fff9-41e5-81f6-9580af7480a7.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCloseConfiguration (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCloseConfiguration (NDIS   5.1)) in Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Irql_Miscellaneous_Function, NdisOpenConfigurationEx
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisCloseConfiguration function
The 
  <b>NdisCloseConfiguration</b> function releases the handle to the registry key that was returned by the 
  <a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a>, 
  <mshelp:link keywords="netvista.ndisopenconfigurationkeybyindex" tabindex="0"><b>
  NdisOpenConfigurationKeyByIndex</b></mshelp:link>, or 
  <mshelp:link keywords="netvista.ndisopenconfigurationkeybyname" tabindex="0"><b>
  NdisOpenConfigurationKeyByName</b></mshelp:link> function.

## Syntax

````
VOID NdisCloseConfiguration(
  _In_ NDIS_HANDLE ConfigurationHandle
);
````

## Parameters

`ConfigurationHandle`

The handle that the 
     <a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a> function
     returns.


## Return Value

None

## Remarks

This function frees any temporary storage allocated in calls to other 
    <b>Ndis<i>Xxx</i></b> functions that required the returned 
    <i>ConfigurationHandle</i> as a parameter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_Miscellaneous_Function, NdisOpenConfigurationEx |

## See Also

<a href="..\ndis\nf-ndis-ndisopenconfigurationex.md">NdisOpenConfigurationEx</a>

<a href="..\ndis\nf-ndis-ndisreadconfiguration.md">NdisReadConfiguration</a>

<a href="..\ndis\nf-ndis-ndisreadnetworkaddress.md">NdisReadNetworkAddress</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<mshelp:link keywords="netvista.ndisopenconfigurationkeybyindex" tabindex="0"><b>
   NdisOpenConfigurationKeyByIndex</b></mshelp:link>

<a href="..\ndis\nc-ndis-protocol_bind_adapter_ex.md">ProtocolBindAdapterEx</a>

<a href="..\ndis\nf-ndis-ndiswriteconfiguration.md">NdisWriteConfiguration</a>

<mshelp:link keywords="netvista.driverentry_of_ndis_protocol_drivers" tabindex="0"><b>DriverEntry of NDIS Protocol
   Drivers</b></mshelp:link>

<mshelp:link keywords="netvista.ndisopenconfigurationkeybyname" tabindex="0"><b>
   NdisOpenConfigurationKeyByName</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCloseConfiguration function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>