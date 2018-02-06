---
UID: NC:wudfworkitem.WUDF_WORKITEM_FUNCTION
title: WUDF_WORKITEM_FUNCTION
author: windows-driver-content
description: A driver's OnWorkItem event callback function performs the work that is associated with a specified work item.
old-location: wdf\onworkitem.htm
old-project: wdf
ms.assetid: 4CCA1F5E-C92E-4D8D-A8C0-B8E9A0F29703
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.onworkitem, OnWorkItem callback function, OnWorkItem, WUDF_WORKITEM_FUNCTION, WUDF_WORKITEM_FUNCTION, wudfworkitem/OnWorkItem, wudfworkitem/PFN_WUDF_WORKITEM, PFN_WUDF_WORKITEM callback function pointer, PFN_WUDF_WORKITEM, umdf.onworkitem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wudfworkitem.h
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wudfworkitem.h
apiname:
-	WUDF_WORKITEM_FUNCTION
product: Windows
targetos: Windows
req.typenames: UNICODE_STRING
req.product: Windows 10 or later.
---


# WUDF_WORKITEM_FUNCTION callback function
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <i>OnWorkItem</i> event callback function performs the work that is associated with a specified work item.

## Syntax

```
WUDF_WORKITEM_FUNCTION WudfWorkitemFunction;

void WudfWorkitemFunction(
  IWDFWorkItem *pWorkItem
)
{...}
```

## Parameters

`*pWorkItem`

A pointer to an  <a href="..\wudfddi\nn-wudfddi-iwdfworkitem.md">IWDFWorkItem</a> interface.


## Return Value

This callback function does not return a value.

## Remarks

To register an <i>OnWorkItem</i> callback function, your driver must place the callback function's address in a <a href="..\wudfworkitem\ns-wudfworkitem-_wudf_workitem_config.md">WUDF_WORKITEM_CONFIG</a> structure before calling <a href="https://msdn.microsoft.com/B34EABF4-C659-4DB4-AEC6-94F544D79221">IWDFDevice3::CreateWorkItem</a>.

Typically, a driver's <i>OnWorkItem</i> callback function performs tasks that are specified by information that the driver stored in the context memory of a work-item object.

The driver must not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560210">IWDFObject::DeleteWdfObject</a> from the <i>OnWorkItem</i> callback function.

For more information, see <a href="https://msdn.microsoft.com/4617A33F-9026-45FF-9CC2-7215423E6D35">Using Work Items</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfworkitem.h |

## See Also

<a href="..\wudfworkitem\ns-wudfworkitem-_wudf_workitem_config.md">WUDF_WORKITEM_CONFIG</a>

<a href="https://msdn.microsoft.com/B34EABF4-C659-4DB4-AEC6-94F544D79221">IWDFDevice3::CreateWorkItem</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560210">IWDFObject::DeleteWdfObject</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WUDF_WORKITEM_FUNCTION callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>