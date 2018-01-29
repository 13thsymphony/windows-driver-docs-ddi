---
UID : NF:wiamdef.wiasGetImageInformation
title : wiasGetImageInformation function
author : windows-driver-content
description : The wiasGetImageInformation function retrieves transfer context information from an item.
old-location : image\wiasgetimageinformation.htm
old-project : image
ms.assetid : 457c4b98-313d-4b31-aa6c-fb62fea6fc7d
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : wiasFncs_6603ae74-b0b9-48f4-9fa9-83cdf3edc1d6.xml, wiasGetImageInformation, wiamdef/wiasGetImageInformation, image.wiasgetimageinformation, wiasGetImageInformation function [Imaging Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wiamdef.h
req.include-header : Wiamdef.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Microsoft Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wiaservc.lib
req.dll : Wiaservc.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DEVICEDIALOGDATA2, *PDEVICEDIALOGDATA2, *LPDEVICEDIALOGDATA2
req.product : Windows 10 or later.
---


# wiasGetImageInformation function
The <b>wiasGetImageInformation </b>function retrieves transfer context information from an item.

## Syntax

````
HRESULT _stdcall wiasGetImageInformation(
  _In_    BYTE                      *pWiasContext,
          LONG                      lFlags,
  _Inout_ PMINIDRV_TRANSFER_CONTEXT pmdtc
);
````

## Parameters

`pWiasContext`

Pointer to a WIA item context.

`lFlags`

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

`pmdtc`

Pointer to a <a href="..\wiamindr_lh\ns-wiamindr_lh-_minidrv_transfer_context.md">MINIDRV_TRANSFER_CONTEXT</a> structure. Upon return, this structure contains the requested image item information.


## Return Value

On success, the function returns S_OK. If the function fails, it returns a standard COM error or one of the WIA_ERROR_XXX errors (described in the Microsoft Windows SDK documentation).

## Remarks

This function uses a <a href="..\wiamindr_lh\ns-wiamindr_lh-_minidrv_transfer_context.md">MINIDRV_TRANSFER_CONTEXT</a> structure to calculate item image and item header sizes. In addition, it can optionally fill in an image header if the image format requires a data header. The header will be copied to the buffer if the <b>pTransferBuffer</b> member of the MINIDRV_TRANSFER_CONTEXT structure is not <b>NULL</b>. When using image formats (such as JPEG) that do not have a header, the header size in the <b>lHeaderSize</b> member of the MINIDRV_TRANSFER_CONTEXT structure is reported as zero.

For image formats where the actual final size of the image is not known until after data acquisition, as with multipage TIFF and compressed formats, the <b>lItemSize</b> member of the <a href="..\wiamindr_lh\ns-wiamindr_lh-_minidrv_transfer_context.md">MINIDRV_TRANSFER_CONTEXT</a> structure is reported as zero. The <b>lImageSize</b> member is reported as the size, in bytes, of the uncompressed image in a single page. 

If WIAS_INIT_CONTEXT is specified in the <i>lFlags</i> parameter, the MINIDRV_TRANSFER_CONTEXT structure pointed to by the <i>pmdtc</i> parameter is filled in with information derived from the item's image properties. This flag should be used when a minidriver has allocated a new context.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wiamdef.h (include Wiamdef.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\wiamindr_lh\ns-wiamindr_lh-_minidrv_transfer_context.md">MINIDRV_TRANSFER_CONTEXT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20wiasGetImageInformation function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>