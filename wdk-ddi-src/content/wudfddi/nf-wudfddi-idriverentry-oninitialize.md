---
UID : NF:wudfddi.IDriverEntry.OnInitialize
title : IDriverEntry::OnInitialize method
author : windows-driver-content
description : The OnInitialize method performs any operations that are necessary to initialize a driver.
old-location : wdf\idriverentry_oninitialize.htm
old-project : wdf
ms.assetid : c676588e-348b-4840-9873-6b1bb2454987
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : IDriverEntry::OnInitialize, OnInitialize method, UMDFDriverObjectRef_01ebb7b4-69bb-4597-b21a-d3ff6cf3bc24.xml, OnInitialize, IDriverEntry, IDriverEntry interface, OnInitialize method, OnInitialize method, IDriverEntry interface, umdf.idriverentry_oninitialize, wdf.idriverentry_oninitialize, wudfddi/IDriverEntry::OnInitialize
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wudfddi.h
req.include-header : Wudfddi.h
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
req.lib : wudfddi.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPOWER_ACTION, POWER_ACTION"
req.product : Windows 10 or later.
---


# OnInitialize method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnInitialize</b> method performs any operations that are necessary to initialize a driver.

## Syntax

````
HRESULT OnInitialize(
  [in] IWDFDriver *pWdfDriver
);
````

## Parameters

`pWdfDriver`

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdriver.md">IWDFDriver</a> interface for the framework driver object that represents the driver that is loaded in the host process.


## Return Value

<b>OnInitialize</b> returns S_OK if the driver completed its global initialization. Otherwise, this method returns one of the error codes that are defined in Winerror.h. If the driver returns an error code, the framework will not load the driver.

## Remarks

The framework creates a new driver object for each driver that is loaded in the driver host process. When a driver enters the system, the framework calls <b>OnInitialize</b> to notify the driver and passes the <a href="..\wudfddi\nn-wudfddi-iwdfdriver.md">IWDFDriver</a> interface in the call.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdfdriver.md">IWDFDriver</a>

<a href="..\wudfddi\nn-wudfddi-idriverentry.md">IDriverEntry</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IDriverEntry::OnInitialize method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>