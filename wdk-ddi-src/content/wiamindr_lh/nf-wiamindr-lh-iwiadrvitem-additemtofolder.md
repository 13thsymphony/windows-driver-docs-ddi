---
UID: NF.wiamindr_lh.IWiaDrvItem.AddItemToFolder
title: IWiaDrvItem::AddItemToFolder
author: windows-driver-content
description: The IWiaDrvItem::AddItemToFolder method adds an IWiaDrvItem item to a folder in a driver item tree.
old-location: image\iwiadrvitem_additemtofolder.htm
old-project: image
ms.assetid: 3f1cd0bf-13ce-49bc-a48e-dc3d89f3c7d7
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: IWiaDrvItem, AddItemToFolder, IWiaDrvItem::AddItemToFolder
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IWiaDrvItem.AddItemToFolder
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
req.iface: IWiaDrvItem
req.product: Windows 10 or later.
---

# IWiaDrvItem::AddItemToFolder method



## -description
<p>The <b>IWiaDrvItem::AddItemToFolder</b> method adds an <b>IWiaDrvItem</b> item to a folder in a driver item tree.</p>


## -syntax

````
HRESULT AddItemToFolder(
  [in, optional] IWiaDrvItem *pIParent
);
````


## -parameters
<dl>

### -param <i>pIParent</i> [in, optional]

<dd>
<p>Points to the <b>IWiaDrvItem</b> parent folder item.</p>
</dd>
</dl>

## -returns
<p>If the method succeeds, it returns S_OK. If the method fails because an invalid <i>pIParent</i> parameter is passed, it returns E_INVALIDARG. If the method fails for another reason, it returns a standard COM error code.</p>

## -remarks
<p>Minidrivers typically use the <b>IWiaDrvItem::AddItemToFolder</b> method to add an item to a parent folder item in a driver item tree. The parent folder item is pointed to by the parameter <i>pIParent</i>. The item pointed to by <i>pIParent</i> must be a folder.</p>

<p>Minidrivers typically use the <b>IWiaDrvItem::AddItemToFolder</b> method to add an item to a parent folder item in a driver item tree. The parent folder item is pointed to by the parameter <i>pIParent</i>. The item pointed to by <i>pIParent</i> must be a folder.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Me and in Windows XP and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543899">IWiaDrvItem::RemoveItemFromFolder</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaDrvItem::AddItemToFolder method%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
