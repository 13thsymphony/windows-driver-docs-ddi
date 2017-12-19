---
UID: NF.wiamdef.wiasUpdateValidFormat
title: wiasUpdateValidFormat function
author: windows-driver-content
description: The wiasUpdateValidFormat function updates the valid format of the property context for the current minidriver.
old-location: image\wiasupdatevalidformat.htm
old-project: Image
ms.assetid: 04e66f34-3771-4b09-b546-f814e4b41906
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: wiasUpdateValidFormat
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
req.alt-api: wiasUpdateValidFormat
req.alt-loc: Wiaservc.dll
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
req.product: Windows 10 or later.
---

# wiasUpdateValidFormat function



## -description
The <b>wiasUpdateValidFormat</b> function updates the valid format of the property context for the current minidriver.



## -syntax

````
HRESULT _stdcall wiasUpdateValidFormat(
  _In_ BYTE                 *pWiasContext,
  _In_ WIA_PROPERTY_CONTEXT *pContext,
  _In_ IWiaMiniDrv          *pIMiniDrv
);
````


## -parameters

### -param pWiasContext [in]

Pointer to a WIA item context.


### -param pContext [in]

Pointer to a <a href="image.wia_property_context">WIA_PROPERTY_CONTEXT</a> structure containing a property context.


### -param pIMiniDrv [in]

Pointer to the <a href="image.iwiaminidrv_interface">IWiaMiniDrv Interface</a> of the current minidriver.


## -returns
On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wiamdef.h (include Wiamdef.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wiaservc.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Wiaservc.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="image.wia_property_context">WIA_PROPERTY_CONTEXT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20wiasUpdateValidFormat function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

