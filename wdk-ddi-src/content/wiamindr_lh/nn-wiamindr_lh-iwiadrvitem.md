---
UID: NN:wiamindr_lh.IWiaDrvItem
title: IWiaDrvItem
author: windows-driver-content
description: The IWiaDrvItem interface provides methods that a WIA minidriver can use to manage a tree of IWiaDrvItem items.
old-location: image\iwiadrvitem_interface.htm
old-project: image
ms.assetid: 0609e1b2-48df-413c-90bd-d7ddea26510a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: DrvItem_9dbe78e4-0823-4edc-b86e-75e25d4de981.xml, IWiaDrvItem, IWiaDrvItem interface [Imaging Devices], IWiaDrvItem interface [Imaging Devices], described, image.iwiadrvitem_interface, wiamindr_lh/IWiaDrvItem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wiamindr_lh.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
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
-	IWiaDrvItem
product: Windows
targetos: Windows
req.typenames: SCANWINDOW, *PSCANWINDOW
req.product: Windows 10 or later.
---

# IWiaDrvItem interface

The <b>IWiaDrvItem</b> interface provides methods that a WIA minidriver can use to manage a tree of <b>IWiaDrvItem</b> items.

## Methods

<p>The <b>IWiaDrvItem</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [IWiaDrvItem::AddItemToFolder](nf-wiamindr_lh-iwiadrvitem-additemtofolder.md) | The AddItemToFolder method adds an IWiaDrvItem item to a folder in a driver item tree. |
| [IWiaDrvItem::DumpItemData](nf-wiamindr_lh-iwiadrvitem-dumpitemdata.md) | The IWiaDrvItem::DumpItemData method dumps private data associated with an IWiaDrvItem item into an allocated private buffer. |
| [IWiaDrvItem::FindChildItemByName](nf-wiamindr_lh-iwiadrvitem-findchilditembyname.md) | The IWiaDrvItem::FindChildItemByName method searches the driver item tree for a specific child item. |
| [IWiaDrvItem::FindItemByName](nf-wiamindr_lh-iwiadrvitem-finditembyname.md) | The IWiaDrvItem::FindItemByName method locates an item in a driver item tree by the item's full name. |
| [IWiaDrvItem::GetDeviceSpecContext](nf-wiamindr_lh-iwiadrvitem-getdevicespeccontext.md) | The IWiaDrvItem::GetDeviceSpecContext method gets a device-specific context. |
| [IWiaDrvItem::GetFirstChildItem](nf-wiamindr_lh-iwiadrvitem-getfirstchilditem.md) | The IWiaDrvItem::GetFirstChildItem method gets the first child item in an IWiaDrvItem folder item. |
| [IWiaDrvItem::GetFullItemName](nf-wiamindr_lh-iwiadrvitem-getfullitemname.md) | The IWiaDrvItem::GetFullItemName method gets the item's full name, including path information. |
| [IWiaDrvItem::GetItemFlags](nf-wiamindr_lh-iwiadrvitem-getitemflags.md) | The IWiaDrvItem::GetItemFlags method gets the item flags of the current IWiaDrvItem item. |
| [IWiaDrvItem::GetItemName](nf-wiamindr_lh-iwiadrvitem-getitemname.md) | The IWiaDrvItem::GetItemName method gets the current IWiaDrvItem item name, not including path information. |
| [IWiaDrvItem::GetNextSiblingItem](nf-wiamindr_lh-iwiadrvitem-getnextsiblingitem.md) | The IWiaDrvItem::GetNextSiblingItem method gets the next sibling of the current item in an IWiaDrvItem folder. |
| [IWiaDrvItem::GetParentItem](nf-wiamindr_lh-iwiadrvitem-getparentitem.md) | The IWiaDrvItem::GetParentItem gets the parent item of the current item. |
| [IWiaDrvItem::RemoveItemFromFolder](nf-wiamindr_lh-iwiadrvitem-removeitemfromfolder.md) | The IWiaDrvItem::RemoveItemFromFolder method removes an item from a parent folder. |
| [IWiaDrvItem::UnlinkItemTree](nf-wiamindr_lh-iwiadrvitem-unlinkitemtree.md) | The IWiaDrvItem::UnlinkItemTree method unlinks the driver item tree and releases all items in the tree. |


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wiamindr_lh.h |