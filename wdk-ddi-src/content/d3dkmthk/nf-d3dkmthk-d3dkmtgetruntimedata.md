---
UID: NF:d3dkmthk.D3DKMTGetRuntimeData
title: D3DKMTGetRuntimeData function
author: windows-driver-content
description: The D3DKMTGetRuntimeData function is for system use only.
old-location: display\d3dkmtgetruntimedata.htm
old-project: display
ms.assetid: a73ebde8-a1d5-4f97-8457-1f01244bb266
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTGetRuntimeData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTGetRuntimeData
req.alt-loc: GDI32.dll,API-MS-Win-dx-d3dkmt-l1-1-0.dll,API-MS-Win-dx-d3dkmt-l1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: GDI32.lib
req.dll: GDI32.dll
req.irql: 
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTGetRuntimeData function



## -description
The <b>D3DKMTGetRuntimeData</b> function is for system use only.



## -syntax

````
NTSTATUS APIENTRY D3DKMTGetRuntimeData(
  _Inout_ const D3DKMT_GETRUNTIMEDATA *pData
);
````


## -parameters

### -param pData [in, out]

Reserved for system use.


## -remarks
This function is reserved for system use.</p>