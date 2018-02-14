---
UID: NF:ks.KsAddObjectCreateItemToObjectHeader
title: KsAddObjectCreateItemToObjectHeader function
author: windows-driver-content
description: The KsAddObjectCreateItemToObjectHeader function adds the specified create-item to an empty item in the previously allocated create item list for this object header.
old-location: stream\ksaddobjectcreateitemtoobjectheader.htm
old-project: stream
ms.assetid: 9946e896-7f1a-4ff2-afa5-9e231047af11
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ksaddobjectcreateitemtoobjectheader, ks/KsAddObjectCreateItemToObjectHeader, ksfunc_de112daa-c37a-4d5b-b646-5fc45fd8ae1c.xml, KsAddObjectCreateItemToObjectHeader function [Streaming Media Devices], KsAddObjectCreateItemToObjectHeader
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsAddObjectCreateItemToObjectHeader
product: Windows
targetos: Windows
req.typenames: 
---


# KsAddObjectCreateItemToObjectHeader function
The <b>KsAddObjectCreateItemToObjectHeader</b> function adds the specified create-item to an empty item in the previously allocated create item list for this object header. An empty item is signified by a <b>NULL</b> create dispatch function in the entry. This function assumes that the caller is serializing multiple changes to the create items list.

## Syntax

````
NTSTATUS KsAddObjectCreateItemToObjectHeader(
  _In_     KSOBJECT_HEADER      Header,
  _In_     PDRIVER_DISPATCH     Create,
  _In_     PVOID                Context,
  _In_     PWSTR                ObjectClass,
  _In_opt_ PSECURITY_DESCRIPTOR SecurityDescriptor
);
````

## Parameters

`Header`

Points to the object header that contains the previously allocated child- create table.

`Create`

Specifies the create dispatch function to use.

`Context`

Specifies the context parameter.

`ObjectClass`

Specifies a pointer to a <b>NULL</b>-terminated character string that is used for comparison on create requests. This pointer must remain valid while the object is active.

`SecurityDescriptor`

Specifies the security descriptor. This must remain valid while the object is active.


## Return Value

The <b>KsAddObjectCreateItemToObjectHeader</b> function returns STATUS_SUCCESS if an empty create item slot was found and the item was added. If unsuccessful, it returns STATUS_ALLOTTED_SPACE_EXCEEDED.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |