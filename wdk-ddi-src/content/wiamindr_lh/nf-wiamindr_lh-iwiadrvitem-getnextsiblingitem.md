---
UID: NF.wiamindr_lh.IWiaDrvItem.GetNextSiblingItem
title: IWiaDrvItem::GetNextSiblingItem method
author: windows-driver-content
description: The IWiaDrvItem::GetNextSiblingItem method gets the next sibling of the current item in an IWiaDrvItem folder.
old-location: image\iwiadrvitem_getnextsiblingitem.htm
old-project: Image
ms.assetid: bc348f40-aaa4-4cd4-9dee-c02748d7412c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IWiaDrvItem, IWiaDrvItem::GetNextSiblingItem, GetNextSiblingItem
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
req.alt-api: IWiaDrvItem.GetNextSiblingItem
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

# IWiaDrvItem::GetNextSiblingItem method



## -description
The <b>IWiaDrvItem::GetNextSiblingItem</b> method gets the next sibling of the current item in an <b>IWiaDrvItem</b> folder.



## -syntax

````
HRESULT GetNextSiblingItem(
  [out, optional] IWiaDrvItem **ppISiblingItem
);
````


## -parameters

### -param ppISiblingItem [out, optional]

Points to a memory location that will receive the address of the <b>IWiaDrvItem</b> object representing the next sibling item in a folder.


## -returns
If the method succeeds, it stores a pointer to the next sibling item in <i>ppISiblingItem</i> and returns S_OK. If there are no more items in the folder, the method returns S_FALSE. If the method fails, it returns a standard COM error code. 


## -remarks
Minidrivers obtain a pointer to the first child item in a folder by calling <a href="image.iwiadrvitem_getfirstchilditem">IWiaDrvItem::GetFirstChildItem</a>. Minidrivers can then obtain the sibling items of this child item in the folder by making successive calls to <b>IWiaDrvItem::GetNextSiblingItem</b>.


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
<a href="image.iwiadrvitem_getfirstchilditem">IWiaDrvItem::GetFirstChildItem</a>
</dt>
<dt>
<a href="image.iwiadrvitem_getparentitem">IWiaDrvItem::GetParentItem</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Image\image]:%20IWiaDrvItem::GetNextSiblingItem method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

