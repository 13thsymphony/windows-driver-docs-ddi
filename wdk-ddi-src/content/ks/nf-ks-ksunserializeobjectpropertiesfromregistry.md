---
UID: NF:ks.KsUnserializeObjectPropertiesFromRegistry
title: KsUnserializeObjectPropertiesFromRegistry function
author: windows-driver-content
description: The KsUnserializeObjectPropertiesFromRegistry function, when given a destination object and a registry path, enumerates the named values and applies them as serialized data to the specified property sets listed in the serialized data.
old-location: stream\ksunserializeobjectpropertiesfromregistry.htm
old-project: stream
ms.assetid: e08ddef7-5942-4943-9dbe-9658279892f0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksfunc_09710ce5-9236-47cc-84b2-4ced36aa654b.xml, KsUnserializeObjectPropertiesFromRegistry, KsUnserializeObjectPropertiesFromRegistry function [Streaming Media Devices], ks/KsUnserializeObjectPropertiesFromRegistry, stream.ksunserializeobjectpropertiesfromregistry
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
-	KsUnserializeObjectPropertiesFromRegistry
product: Windows
targetos: Windows
req.typenames: 
---


# KsUnserializeObjectPropertiesFromRegistry function
The <b>KsUnserializeObjectPropertiesFromRegistry</b> function, when given a destination object and a registry path, enumerates the named values and applies them as serialized data to the specified property sets listed in the serialized data. An IRP is generated when sending the serialized data, so no assumption is made on use of KS property structures to internally define the property sets. The function does not use the names of the values.

## Syntax

````
NTSTATUS KsUnserializeObjectPropertiesFromRegistry(
  _In_     PFILE_OBJECT    FileObject ,
  _In_opt_ HANDLE          ParentKey ,
  _In_opt_ PUNICODE_STRING RegistryPath 
);
````

## Parameters

`FileObject`

Specifies the file object whose properties are being set.

`ParentKey`

Optionally contains a handle to the parent of the path, or <b>NULL</b>. The Parent Key and/or the <i>RegistryPath</i> must be passed.

`RegistryPath`

Optionally contains the path to the key whose subkeys will be enumerated as property sets, or otherwise <b>NULL</b>. The <i>ParentKey</i> and/or the Registry Path must be passed.


## Return Value

The <b>KsUnserializeObjectPropertiesFromRegistry</b> function returns STATUS_SUCCESS if the property sets were unserialized. The function returns an error if the registry path was invalid, one of the subkeys was invalid, setting a property was unsuccessful, the serialized format was invalid, or a property set was not supported on the object.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |