---
UID: NF:filterpipeline.IPrintPipelinePropertyBag.DeleteProperty
title: IPrintPipelinePropertyBag::DeleteProperty method
author: windows-driver-content
description: The DeleteProperty method deletes a property from a property bag.
old-location: print\iprintpipelinepropertybag_deleteproperty.htm
old-project: print
ms.assetid: f3de5514-9a7f-4e27-9be0-4aec4b84a5a7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DeleteProperty method [Print Devices], DeleteProperty method [Print Devices], IPrintPipelinePropertyBag interface, DeleteProperty,IPrintPipelinePropertyBag.DeleteProperty, IPrintPipelinePropertyBag, IPrintPipelinePropertyBag interface [Print Devices], DeleteProperty method, IPrintPipelinePropertyBag::DeleteProperty, filterpipeline/IPrintPipelinePropertyBag::DeleteProperty, filterpipeline_816db2e4-811c-467f-a7c3-65d2e35c0107.xml, print.iprintpipelinepropertybag_deleteproperty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: filterpipeline.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	filterpipeline.h
api_name:
-	IPrintPipelinePropertyBag.DeleteProperty
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# DeleteProperty method
The <code>DeleteProperty</code> method deletes a property from a property bag.

## Syntax

````
BOOL DeleteProperty(
  [in] const wchar_t *pszName
);
````

## Parameters

`pszName`

The name of the property to delete from the property bag.


## Return Value

<code>DeleteProperty</code> returns "true" if the property was deleted from the property bag.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |
| **Library** | filterpipeline.h |