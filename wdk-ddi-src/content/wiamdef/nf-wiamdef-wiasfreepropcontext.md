---
UID: NF:wiamdef.wiasFreePropContext
title: wiasFreePropContext function
author: windows-driver-content
description: The wiasFreePropContext function releases the memory occupied by a WIA_PROPERTY_CONTEXT structure.
old-location: image\wiasfreepropcontext.htm
old-project: image
ms.assetid: 14a1a5bd-acc3-4ca6-87c6-5326c0f9ca82
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: image.wiasfreepropcontext, wiamdef/wiasFreePropContext, wiasFncs_60deac65-fa17-4f2e-abe1-fa6d424dc477.xml, wiasFreePropContext, wiasFreePropContext function [Imaging Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiamdef.h
req.include-header: Wiamdef.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
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
req.lib: Wiaservc.lib
req.dll: Wiaservc.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Wiaservc.dll
api_name:
-	wiasFreePropContext
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---


# wiasFreePropContext function
The <b>wiasFreePropContext </b>function releases the memory occupied by a <a href="..\wiamindr_lh\ns-wiamindr_lh-_wia_property_context.md">WIA_PROPERTY_CONTEXT</a> structure.

## Syntax

````
HRESULT _stdcall wiasFreePropContext(
  _Inout_ WIA_PROPERTY_CONTEXT *pContext
);
````

## Parameters

`pContext`

Pointer to a <a href="..\wiamindr_lh\ns-wiamindr_lh-_wia_property_context.md">WIA_PROPERTY_CONTEXT</a> structure that contains a property context.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | wiamdef.h (include Wiamdef.h) |
| **Library** | Wiaservc.lib |
| **DLL** | Wiaservc.dll |

## See Also

<a href="..\wiamindr_lh\ns-wiamindr_lh-_wia_property_context.md">WIA_PROPERTY_CONTEXT</a>



<a href="..\wiamdef\nf-wiamdef-wiascreatepropcontext.md">wiasCreatePropContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasFreePropContext function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>