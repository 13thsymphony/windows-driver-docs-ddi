---
UID: NF.wiamindr_lh.IWiaDrvItem.FindItemByName
title: IWiaDrvItem::FindItemByName method
author: windows-driver-content
description: The IWiaDrvItem::FindItemByName method locates an item in a driver item tree by the item's full name.
old-location: image\iwiadrvitem_finditembyname.htm
old-project: Image
ms.assetid: 59a77753-1f34-4224-af11-c6bbfa847619
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IWiaDrvItem, IWiaDrvItem::FindItemByName, FindItemByName
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
req.alt-api: IWiaDrvItem.FindItemByName
req.alt-loc: wiamindr_lh.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# IWiaDrvItem::FindItemByName method



## -description
The<b> IWiaDrvItem::FindItemByName</b> method locates an item in a driver item tree by the item's full name.



## -syntax

````
HRESULT FindItemByName(
  [in]            LONG        lFlags,
  [in]            BSTR        bstrFullItemName,
  [out, optional] IWiaDrvItem **ppItem
);
````


## -parameters

### -param lFlags [in]

Reserved. Set to zero. 


### -param bstrFullItemName [in]

Specifies the full name of the item to find.


### -param ppItem [out, optional]

Points to a memory location that will receive the address of the found <b>IWiaDrvItem</b> item. 


## -returns
If the method succeeds, it stores a pointer to the found item in <i>ppItem</i> and returns S_OK. If the method fails, it places <b>NULL</b> in <i>ppItem</i> and returns S_FALSE. If this method does not find the required item, it returns S_FALSE. If an error occurred during the search, a standard COM error code will be returned.


## -remarks
Minidrivers call this method to find an item in a driver item tree when the item's full name is known. The item's full name is obtained in the method <a href="image.iwiadrvitem_getfullitemname">IWiaDrvItem::GetFullItemName</a>.

This method starts the search for the specified item at the root item in the driver item tree.


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
Available in Windows Me and in Windows XP and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wiamindr_lh.h (include Wiamindr.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="image.iwiadrvitem_findchilditembyname">IWiaDrvItem::FindChildItemByName</a>
</dt>
<dt>
<a href="image.iwiadrvitem_getfullitemname">IWiaDrvItem::GetFullItemName</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20IWiaDrvItem::FindItemByName method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

