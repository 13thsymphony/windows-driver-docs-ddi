---
UID: NF:wiamindr_lh.IWiaDrvItem.FindChildItemByName
title: IWiaDrvItem::FindChildItemByName method
author: windows-driver-content
description: The IWiaDrvItem::FindChildItemByName method searches the driver item tree for a specific child item.
old-location: image\iwiadrvitem_findchilditembyname.htm
old-project: image
ms.assetid: 04f446f2-cd59-4191-be0c-60140ecee3b2
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: DrvItem_afe8c47f-ebf9-484e-94bf-fdcd4713ea2a.xml, FindChildItemByName method [Imaging Devices], FindChildItemByName method [Imaging Devices], IWiaDrvItem interface, FindChildItemByName,IWiaDrvItem.FindChildItemByName, IWiaDrvItem, IWiaDrvItem interface [Imaging Devices], FindChildItemByName method, IWiaDrvItem::FindChildItemByName, image.iwiadrvitem_findchilditembyname, wiamindr_lh/IWiaDrvItem::FindChildItemByName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
req.lib: wiamindr_lh.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	wiamindr_lh.h
api_name:
-	IWiaDrvItem.FindChildItemByName
product: Windows
targetos: Windows
req.typenames: SCANWINDOW, *PSCANWINDOW
req.product: Windows 10 or later.
---


# FindChildItemByName method
The <b>IWiaDrvItem::FindChildItemByName</b> method searches the driver item tree for a specific child item.

## Syntax

````
HRESULT FindChildItemByName(
  [in]            BSTR        bstrChildItemName,
  [out, optional] IWiaDrvItem **ppIChildItem
);
````

## Parameters

`__MIDL__IWiaDrvItem0010`



`__MIDL__IWiaDrvItem0011`




## Return Value

If the method succeeds, it stores a pointer to the found child item in <i>ppIChildItem</i> and returns S_OK. If the method fails to find the child item, it returns S_FALSE. If the method fails for another reason, it returns a standard COM error code.

## Remarks

Minidrivers typically use this method to search a driver item tree for a specific child item when the child item's name is known. The child item's full name is obtained in the  method <a href="https://msdn.microsoft.com/library/windows/hardware/ff543881">IWiaDrvItem::GetFullItemName</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me and in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | wiamindr_lh.h (include Wiamindr.h) |
| **Library** | wiamindr_lh.h |

## See Also

<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiadrvitem.md">IWiaDrvItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543870">IWiaDrvItem::FindItemByName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543881">IWiaDrvItem::GetFullItemName</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaDrvItem::FindChildItemByName method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>