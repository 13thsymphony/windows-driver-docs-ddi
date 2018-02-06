---
UID: NF:wudfddi.IWDFDevice3.CreateWorkItem
title: IWDFDevice3::CreateWorkItem method
author: windows-driver-content
description: The CreateWorkItem method creates a framework work-item object, which can subsequently be added to the framework’s work-item queue.
old-location: wdf\iwdfdevice3_createworkitem.htm
old-project: wdf
ms.assetid: B34EABF4-C659-4DB4-AEC6-94F544D79221
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.iwdfdevice3_createworkitem, IWDFDevice3::CreateWorkItem, CreateWorkItem method, IWDFDevice3 interface, wudfddi/IWDFDevice3::CreateWorkItem, CreateWorkItem method, IWDFDevice3 interface, CreateWorkItem method, CreateWorkItem, umdf.iwdfdevice3_createworkitem, IWDFDevice3
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFDevice3.CreateWorkItem
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# CreateWorkItem method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateWorkItem</b> method creates a framework work-item object, which can subsequently be added to the framework’s work-item queue.

## Syntax

````
HRESULT CreateWorkItem(
  [in]           PWUDF_WORKITEM_CONFIG pConfig,
  [in, optional] IWDFObject            *pParentObject,
  [out]          IWDFWorkItem          **ppWorkItem
);
````

## Parameters

`pConfig`

A pointer to a caller-allocated <a href="..\wudfworkitem\ns-wudfworkitem-_wudf_workitem_config.md">WUDF_WORKITEM_CONFIG</a> structure that the driver must have already initialized by calling <a href="..\wudfworkitem\nf-wudfworkitem-wudf_workitem_config_init.md">WUDF_WORKITEM_CONFIG_INIT</a>.

`pParentObject`

A pointer to the parent object interface or NULL.

`ppWorkItem`

A pointer to a buffer that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfworkitem.md">IWDFWorkItem</a> interface for the new WorkItem object.


## Return Value

The method returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## Remarks

If you specify a parent object, the framework automatically deletes the work-item when the parent object is deleted. Alternatively, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560210">IWDFObject::DeleteWdfObject</a> to delete a work-item. The driver must not delete a work-item in its <a href="..\wudfworkitem\nc-wudfworkitem-wudf_workitem_function.md">OnWorkItem</a> callback function.

For more information, see <a href="https://msdn.microsoft.com/4617A33F-9026-45FF-9CC2-7215423E6D35">Using Work Items</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi.h |
| **Library** | wudfddi.h |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfworkitem\ns-wudfworkitem-_wudf_workitem_config.md">WUDF_WORKITEM_CONFIG</a>

<a href="..\wudfddi\nn-wudfddi-iwdfdevice3.md">IWDFDevice3</a>

<a href="..\wudfworkitem\nc-wudfworkitem-wudf_workitem_function.md">OnWorkItem</a>

<a href="..\wudfworkitem\nf-wudfworkitem-wudf_workitem_config_init.md">WUDF_WORKITEM_CONFIG_INIT</a>

<a href="..\wudfddi\nn-wudfddi-iwdfworkitem.md">IWDFWorkItem</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice3::CreateWorkItem method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>