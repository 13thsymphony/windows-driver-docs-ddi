---
UID : NF:wdfdriver.WdfGetDriver
title : WdfGetDriver function
author : windows-driver-content
description : The WdfGetDriver method returns a handle to the framework driver object that represents the calling driver.
old-location : wdf\wdfgetdriver.htm
old-project : wdf
ms.assetid : 423d4407-9e30-4625-bbe8-5465af29cfaa
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfGetDriver, wdfdriver/WdfGetDriver, DFDriverObjectRef_7419a365-e5ee-49cd-8d85-4db65cd27645.xml, kmdf.wdfgetdriver, PFN_WDFGETDRIVER, wdf.wdfgetdriver, WdfGetDriver method
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfdriver.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll : 
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_DRIVER_INIT_FLAGS
req.product : Windows 10 or later.
---


# WdfGetDriver function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfGetDriver</b> method returns a handle to the framework driver object that represents the calling driver.

## Syntax

````
WDFDRIVER WdfGetDriver(void);
````

## Parameters

This function has no parameters.

## Return Value

<b>WdfGetDriver</b> returns a handle to a framework driver object, or <b>NULL</b> if the driver has not called <a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdriver.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | Any level |

## See Also

<a href="..\wdfdriver\nf-wdfdriver-wdfdrivercreate.md">WdfDriverCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfGetDriver method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>