---
UID : NF:wdfwmi.WdfWmiInstanceGetProvider
title : WdfWmiInstanceGetProvider function
author : windows-driver-content
description : The WdfWmiInstanceGetProvider method returns a handle to the WMI provider object that is the parent object of a specified WMI instance object.
old-location : wdf\wdfwmiinstancegetprovider.htm
old-project : wdf
ms.assetid : e0371aeb-fcc0-4749-b70e-26b05b4f12b2
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.wdfwmiinstancegetprovider, PFN_WDFWMIINSTANCEGETPROVIDER, WdfWmiInstanceGetProvider method, DFWMIRef_f5950eae-6036-4acc-91ab-d7d49ae74202.xml, WdfWmiInstanceGetProvider, kmdf.wdfwmiinstancegetprovider, wdfwmi/WdfWmiInstanceGetProvider
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfwmi.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : <=DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_WMI_PROVIDER_FLAGS
req.product : Windows 10 or later.
---


# WdfWmiInstanceGetProvider function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfWmiInstanceGetProvider</b> method returns a handle to the WMI provider object that is the parent object of a specified WMI instance object.

## Syntax

````
WDFWMIPROVIDER WdfWmiInstanceGetProvider(
  _In_ WDFWMIINSTANCE WmiInstance
);
````

## Parameters

`WmiInstance`

A handle to a WMI instance object that the driver obtained from a previous call to <a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>.


## Return Value

<b>WdfWmiInstanceGetProvider</b> returns a handle to a WMI provider object.

A bug check occurs if the driver supplies an invalid object handle.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfwmi.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfwmi\nf-wdfwmi-wdfwmiinstancecreate.md">WdfWmiInstanceCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfWmiInstanceGetProvider method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>