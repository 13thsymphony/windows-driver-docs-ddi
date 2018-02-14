---
UID: NF:wiautil.wiauGetDrvItemContext
title: wiauGetDrvItemContext function
author: windows-driver-content
description: The wiauGetDrvItemContext function gets the driver item context, and optionally, the driver item.
old-location: image\wiaugetdrvitemcontext.htm
old-project: image
ms.assetid: 6d4b7a25-436f-4547-8969-66dd45fa46fd
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiauFncs_3928edcb-8885-456a-a27d-62612fcb2d1a.xml, wiautil/wiauGetDrvItemContext, wiauGetDrvItemContext, image.wiaugetdrvitemcontext, wiauGetDrvItemContext function [Imaging Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wiautil.h
apiname:
-	wiauGetDrvItemContext
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# wiauGetDrvItemContext function
The <b>wiauGetDrvItemContext</b> function gets the driver item context, and optionally, the driver item.

## Syntax

````
HRESULT _stdcall wiauGetDrvItemContext(
  _In_    BYTE                  *pWiasContext,
  _Inout_ VOID                  **ppItemCtx,
  _Inout_ IWiaDrvItem ppDrvItem **ppDrvItem
);
````

## Parameters

`pWiasContext`

Pointer to a WIA item context.

`ppItemCtx`

Pointer to a memory location that receives a pointer to the driver item context.

`ppDrvItem`

<i>Optional</i>. Pointer to a memory location that receives a pointer to a driver item. The default value of this parameter is <b>NULL</b>, which means that when this function returns, no change is made to this parameter.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later. Available in Windows XP and later. |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h) |
| **Library** | NtosKrnl.exe |