---
UID: NS.D3DKMTHK._D3DKMT_CREATEBUNDLEOBJECT
title: _D3DKMT_CREATEBUNDLEOBJECT
author: windows-driver-content
description: Holds information to create a bundle object.
old-location: display\d3dkmt-createbundleobject.htm
old-project: display
ms.assetid: dbb01112-9d28-4dbf-88c7-3304d9d6a661
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DKMT_CREATEBUNDLEOBJECT, D3DKMT_CREATEBUNDLEOBJECT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_CREATEBUNDLEOBJECT
req.alt-loc: d3dkmthk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# _D3DKMT_CREATEBUNDLEOBJECT structure



## -description
Holds information to create a bundle object.



## -syntax

````
typedef struct _D3DKMT_CREATEBUNDLEOBJECT {
  UINT                cObjects;
  const D3DKMT_HANDLE *phObjects;
  POBJECT_ATTRIBUTES  *ppObjectAttributes;
  POBJECT_ATTRIBUTES  pBundleObjectAttributes;
  DWORD                dwBundleDesiredAccess;
  HANDLE              hNtBundleHandle;
} D3DKMT_CREATEBUNDLEOBJECT, D3DKMT_CREATEBUNDLEOBJECT;
````


## -struct-fields

### -field cObjects

The number of the DXGK object to be bundled.


### -field phObjects

A pointer to the array of the DXGK object to be bundled.


### -field ppObjectAttributes

An array of pointers to object attributes for DXGK objects.


### -field pBundleObjectAttributes

Object attributes for the bundled object.


### -field  dwBundleDesiredAccess

The desired access for bundle handle.


### -field hNtBundleHandle

The NT bundle handle.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h</dt>
</dl>
</td>
</tr>
</table>