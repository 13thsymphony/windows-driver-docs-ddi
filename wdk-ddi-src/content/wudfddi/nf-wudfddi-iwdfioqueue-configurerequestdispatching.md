---
UID : NF:wudfddi.IWDFIoQueue.ConfigureRequestDispatching
title : IWDFIoQueue::ConfigureRequestDispatching method
author : windows-driver-content
description : The ConfigureRequestDispatching method configures the queuing of I/O requests of the given type.
old-location : wdf\iwdfioqueue_configurerequestdispatching.htm
old-project : wdf
ms.assetid : 376b0cc3-8189-499e-ad7f-5844f8cb4221
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : ConfigureRequestDispatching method, IWDFIoQueue interface, wudfddi/IWDFIoQueue::ConfigureRequestDispatching, umdf.iwdfioqueue_configurerequestdispatching, IWDFIoQueue, UMDFQueueObjectRef_8aab2e0a-7864-4a37-abba-2807327dd4dc.xml, ConfigureRequestDispatching, IWDFIoQueue interface, ConfigureRequestDispatching method, wdf.iwdfioqueue_configurerequestdispatching, ConfigureRequestDispatching method, IWDFIoQueue::ConfigureRequestDispatching
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wudfddi.h
req.include-header : Wudfddi.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.5
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : wudfddi.h
req.dll : WUDFx.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : POWER_ACTION, *PPOWER_ACTION
req.product : Windows 10 or later.
---


# ConfigureRequestDispatching method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>ConfigureRequestDispatching</b> method configures the queuing of I/O requests of the given type.

## Syntax

````
HRESULT ConfigureRequestDispatching(
  [in] WDF_REQUEST_TYPE RequestType,
  [in] BOOL             Forward
);
````

## Parameters

`RequestType`

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_type.md">WDF_REQUEST_TYPE</a>-typed value that identifies the request type to be queued. The only valid values are <b>WdfRequestCreate</b>, <b>WdfRequestRead</b>, <b>WdfRequestWrite</b>, and <b>WdfRequestDeviceIoControl</b>.

`Forward`

A BOOL value that specifies whether requests of the specified type are queued. <b>TRUE</b> indicates to enable queuing requests; <b>FALSE</b> indicates to disable queuing requests.


## Return Value

<b>ConfigureRequestDispatching</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## Remarks

The driver can call the <b>ConfigureRequestDispatching</b> method multiple times to configure how each request type is dispatched to the I/O queue.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **Library** | wudfddi.h |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_type.md">WDF_REQUEST_TYPE</a>

<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoQueue::ConfigureRequestDispatching method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>