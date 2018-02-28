---
UID: NF:wiautil.wiauGetResourceString
title: wiauGetResourceString function
author: windows-driver-content
description: The wiauGetResourceString function gets a resource string, storing it as a BSTR.
old-location: image\wiaugetresourcestring.htm
old-project: image
ms.assetid: b042702a-46ff-4ec9-8a92-af8516802e64
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: image.wiaugetresourcestring, wiauFncs_aa163759-0e49-4612-9f6c-78bd6534a62e.xml, wiauGetResourceString, wiauGetResourceString function [Imaging Devices], wiautil/wiauGetResourceString
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wiautil.h
api_name:
-	wiauGetResourceString
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# wiauGetResourceString function
The <b>wiauGetResourceString</b> function gets a resource string, storing it as a <b>BSTR</b>.

## Syntax

````
HRESULT _stdcall wiauGetResourceString(
        HINSTANCE hInst,
        LONG      lResourceID,
  _Out_ BSTR      *pbstrStr
);
````

## Parameters

`hInst`

Specifies the handle of the module instance.

`lResourceID`

Specifies the resource ID of the target BSTR value.

`pbstrStr`

Points to the memory location that receives the retrieved string. The caller of this function must free this string by calling <b>SysFreeString</b> (described in the Microsoft Windows SDK documentation).


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h) |
| **Library** | NtosKrnl.exe |