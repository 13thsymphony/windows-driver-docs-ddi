---
UID: NF.wiamdef.wiasGetImageInformation
title: wiasGetImageInformation function
author: windows-driver-content
description: The wiasGetImageInformation function retrieves transfer context information from an item.
old-location: image\wiasgetimageinformation.htm
old-project: Image
ms.assetid: 457c4b98-313d-4b31-aa6c-fb62fea6fc7d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: wiasGetImageInformation
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
req.alt-api: wiasGetImageInformation
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

# wiasGetImageInformation function



## -description
The <b>wiasGetImageInformation </b>function retrieves transfer context information from an item.



## -syntax

````
HRESULT _stdcall wiasGetImageInformation(
  _In_    BYTE                      *pWiasContext,
          LONG                      lFlags,
  _Inout_ PMINIDRV_TRANSFER_CONTEXT pmdtc
);
````


## -parameters

### -param pWiasContext [in]

Pointer to a WIA item context.


### -param lFlags 

Specifies operational flags. Currently, only the following flag is defined:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
WIAS_INIT_CONTEXT

</td>
<td>
Initialize the MINIDRV_TRANSFER_CONTEXT structure.

</td>
</tr>
</table>
 


### -param pmdtc [in, out]

Pointer to a <a href="image.minidrv_transfer_context">MINIDRV_TRANSFER_CONTEXT</a> structure. Upon return, this structure contains the requested image item information.


## -returns
On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).


## -remarks
This function uses a <a href="image.minidrv_transfer_context">MINIDRV_TRANSFER_CONTEXT</a> structure to calculate item image and item header sizes. In addition, it can optionally fill in an image header if the image format requires a data header. The header will be copied to the buffer if the <b>pTransferBuffer</b> member of the MINIDRV_TRANSFER_CONTEXT structure is not <b>NULL</b>. When using image formats (such as JPEG) that do not have a header, the header size in the <b>lHeaderSize</b> member of the MINIDRV_TRANSFER_CONTEXT structure is reported as zero.

For image formats where the actual final size of the image is not known until after data acquisition, as with multipage TIFF and compressed formats, the <b>lItemSize</b> member of the <a href="image.minidrv_transfer_context">MINIDRV_TRANSFER_CONTEXT</a> structure is reported as zero. The <b>lImageSize</b> member is reported as the size, in bytes, of the uncompressed image in a single page. 

If WIAS_INIT_CONTEXT is specified in the <i>lFlags</i> parameter, the MINIDRV_TRANSFER_CONTEXT structure pointed to by the <i>pmdtc</i> parameter is filled in with information derived from the item's image properties. This flag should be used when a minidriver has allocated a new context.


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
<a href="image.minidrv_transfer_context">MINIDRV_TRANSFER_CONTEXT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20wiasGetImageInformation function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

