---
UID: NF:wudfddi.IWDFWorkItem.GetParentObject
title: IWDFWorkItem::GetParentObject method
author: windows-driver-content
description: The GetParentObject method returns the parent framework object of this interface's work item.
old-location: wdf\iwdfworkitem_getparentobject.htm
old-project: wdf
ms.assetid: D965D8D3-B78C-4126-A675-D6D8A85AA158
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetParentObject method, GetParentObject method, IWDFWorkItem interface, GetParentObject,IWDFWorkItem.GetParentObject, IWDFWorkItem, IWDFWorkItem interface, GetParentObject method, IWDFWorkItem::GetParentObject, umdf.iwdfworkitem_getparentobject, wdf.iwdfworkitem_getparentobject, wudfddi/IWDFWorkItem::GetParentObject
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
-	IWDFWorkItem.GetParentObject
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# GetParentObject method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetParentObject</b> method returns the parent framework object of this interface's  work item.

## Syntax

````
IWDFObject* GetParentObject();
````

## Parameters

This function has no parameters.

## Return Value

A pointer to the parent object interface.

## Remarks

For more information, see <a href="https://msdn.microsoft.com/4617A33F-9026-45FF-9CC2-7215423E6D35">Using Work Items</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi.h |
| **DLL** | WUDFx.dll |

## See Also

<a href="..\wudfddi\nn-wudfddi-iwdfworkitem.md">IWDFWorkItem</a>