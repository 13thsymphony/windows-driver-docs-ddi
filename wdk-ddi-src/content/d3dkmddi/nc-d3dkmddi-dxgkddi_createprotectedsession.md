---
UID: NC:d3dkmddi.DXGKDDI_CREATEPROTECTEDSESSION
title: DXGKDDI_CREATEPROTECTEDSESSION function
author: windows-driver-content
description: Used to create a protected session.
old-location: display\dxgkddi_createprotectedsession.htm
old-project: display
ms.assetid: 0FAE7AA0-839D-4D21-BC10-46B2B651979F
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKDDI_CREATEPROTECTEDSESSION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKDDI_CREATEPROTECTEDSESSION
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: requires_(PASSIVE_LEVEL)
req.typenames: D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032
---

# DXGKDDI_CREATEPROTECTEDSESSION function



## -description
Used to create a protected session.



## -syntax

````
NTSTATUS APIENTRY DXGKDDI_CREATEPROTECTEDSESSION(
  _In_    const HANDLE                           hAdapter,
  _Inout_       PDXGKARG_CREATEPROTECTEDSESSION  pCreateProtectedSession
);
````


## -parameters

### -param hAdapter [in]

A handle to the adapter.


### -param pCreateProtectedSession [in, out]

A pointer to the arguments used to create a protected session.


## -returns
Returns STATUS_SUCCESS if completed successfully.


## -remarks
