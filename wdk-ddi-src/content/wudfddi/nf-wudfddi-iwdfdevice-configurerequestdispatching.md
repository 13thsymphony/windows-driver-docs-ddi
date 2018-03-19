---
UID: NF:wudfddi.IWDFDevice.ConfigureRequestDispatching
title: IWDFDevice::ConfigureRequestDispatching method
author: windows-driver-content
description: The ConfigureRequestDispatching method configures the queuing of I/O requests of the specified type to the specified I/O queue.
old-location: wdf\iwdfdevice_configurerequestdispatching.htm
old-project: wdf
ms.assetid: b3318695-e9f2-480a-9133-9008ef0002b7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ConfigureRequestDispatching method, ConfigureRequestDispatching method, IWDFDevice interface, ConfigureRequestDispatching,IWDFDevice.ConfigureRequestDispatching, IWDFDevice, IWDFDevice interface, ConfigureRequestDispatching method, IWDFDevice::ConfigureRequestDispatching, UMDFDeviceObjectRef_1fbf31c6-856c-45d2-aa86-3b36372821c8.xml, umdf.iwdfdevice_configurerequestdispatching, wdf.iwdfdevice_configurerequestdispatching, wudfddi/IWDFDevice::ConfigureRequestDispatching
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFDevice.ConfigureRequestDispatching
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# ConfigureRequestDispatching method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>ConfigureRequestDispatching</b> method configures the queuing of I/O requests of the specified type to the specified I/O queue.

## Syntax

````
HRESULT ConfigureRequestDispatching(
  [in] IWDFIoQueue      *pQueue,
  [in] WDF_REQUEST_TYPE RequestType,
  [in] BOOL             Forward
);
````

## Parameters

`pQueue`

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a> interface for the I/O queue to configure.

`RequestType`

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_type.md">WDF_REQUEST_TYPE</a>-typed value that identifies the request type to be queued. The only valid <b>WDF_REQUEST_TYPE</b> values are <b>WdfRequestCreate</b>, <b>WdfRequestRead</b>, <b>WdfRequestWrite</b>, and <b>WdfRequestDeviceIoControl</b>.

`Forward`

A BOOL value that specifies whether requests of the specified type are queued. <b>TRUE</b> indicates to enable queuing requests; <b>FALSE</b> indicates to disable queuing requests.


## Return Value

<b>ConfigureRequestDispatching</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfddi_types\ne-wudfddi_types-_wdf_request_type.md">WDF_REQUEST_TYPE</a>



<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a>