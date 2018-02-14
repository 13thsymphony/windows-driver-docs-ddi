---
UID: NF:wdfobject.WDF_TYPE_NAME_TO_TYPE_INFO
title: WDF_TYPE_NAME_TO_TYPE_INFO macro
author: windows-driver-content
description: This macro is reserved for internal use only.
old-location: wdf\wdf_type_name_to_type_info.htm
old-project: wdf
ms.assetid: e0ebbfee-cf47-4bcc-a828-13d51ba14622
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_TYPE_NAME_TO_TYPE_INFO macro, kmdf.wdf_type_name_to_type_info, DFGenObjectRef_4f9f25c8-aa26-478f-a8e8-a83e979c109b.xml, wdfobject/WDF_TYPE_NAME_TO_TYPE_INFO, wdf.wdf_type_name_to_type_info, WDF_TYPE_NAME_TO_TYPE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdfobject.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WDF_GET_CONTEXT_TYPE_INFO
product: Windows
targetos: Windows
req.typenames: WDF_SYNCHRONIZATION_SCOPE
req.product: Windows 10 or later.
---


# WDF_TYPE_NAME_TO_TYPE_INFO function
This macro is reserved for internal use only.

## Syntax

````
void WDF_GET_CONTEXT_TYPE_INFO(
    _contexttype
);
````

## Parameters

`_contexttype`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wdfobject.h |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |