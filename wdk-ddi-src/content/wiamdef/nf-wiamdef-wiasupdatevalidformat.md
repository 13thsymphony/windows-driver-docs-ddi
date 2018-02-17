---
UID: NF:wiamdef.wiasUpdateValidFormat
title: wiasUpdateValidFormat function
author: windows-driver-content
description: The wiasUpdateValidFormat function updates the valid format of the property context for the current minidriver.
old-location: image\wiasupdatevalidformat.htm
old-project: image
ms.assetid: 04e66f34-3771-4b09-b546-f814e4b41906
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wiasUpdateValidFormat, image.wiasupdatevalidformat, wiamdef/wiasUpdateValidFormat, wiasUpdateValidFormat function [Imaging Devices], wiasFncs_dfbd0aa5-1c7c-4b4f-a1da-82176b36e914.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Wiaservc.dll
apiname:
-	wiasUpdateValidFormat
product: Windows
targetos: Windows
req.typenames: DEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2
req.product: Windows 10 or later.
---


# wiasUpdateValidFormat function
The <b>wiasUpdateValidFormat</b> function updates the valid format of the property context for the current minidriver.

## Syntax

````
HRESULT _stdcall wiasUpdateValidFormat(
  _In_ BYTE                 *pWiasContext,
  _In_ WIA_PROPERTY_CONTEXT *pContext,
  _In_ IWiaMiniDrv          *pIMiniDrv
);
````

## Parameters

`pWiasContext`

Pointer to a WIA item context.

`pContext`

Pointer to a <a href="..\wiamindr_lh\ns-wiamindr_lh-_wia_property_context.md">WIA_PROPERTY_CONTEXT</a> structure containing a property context.

`pIMiniDrv`

Pointer to the <a href="..\wiamindr_lh\nn-wiamindr_lh-iwiaminidrv.md">IWiaMiniDrv Interface</a> of the current minidriver.


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasUpdateValidFormat function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>