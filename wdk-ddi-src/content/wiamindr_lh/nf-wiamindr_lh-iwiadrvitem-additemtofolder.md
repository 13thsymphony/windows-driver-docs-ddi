---
UID: NF:wiamindr_lh.IWiaDrvItem.AddItemToFolder
title: IWiaDrvItem::AddItemToFolder method
author: windows-driver-content
description: The AddItemToFolder method adds an IWiaDrvItem item to a folder in a driver item tree.
old-location: image\iwiadrvitem_additemtofolder.htm
old-project: image
ms.assetid: 3f1cd0bf-13ce-49bc-a48e-dc3d89f3c7d7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: AddItemToFolder method [Imaging Devices], AddItemToFolder method [Imaging Devices], IWiaDrvItem interface, AddItemToFolder,IWiaDrvItem.AddItemToFolder, DrvItem_7979b3e5-dfd3-41bb-ae55-266cbb74866c.xml, IWiaDrvItem, IWiaDrvItem interface [Imaging Devices], AddItemToFolder method, IWiaDrvItem::AddItemToFolder, image.iwiadrvitem_additemtofolder, wiamindr_lh/IWiaDrvItem::AddItemToFolder
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
-	IWiaDrvItem.AddItemToFolder
product:
- Windows
targetos: Windows
req.typenames: SCANWINDOW, *PSCANWINDOW
req.product: Windows 10 or later.
---


# IWiaDrvItem::AddItemToFolder method
The AddItemToFolder method adds an IWiaDrvItem item to a folder in a driver item tree.

## Syntax

```
HRESULT AddItemToFolder(
  IWiaDrvItem *__MIDL__IWiaDrvItem0004
);
```

## Parameters

`__MIDL__IWiaDrvItem0004`




## Return Value

If the method succeeds, it returns S_OK. If the method fails because an invalid <i>pIParent</i> parameter is passed, it returns E_INVALIDARG. If the method fails for another reason, it returns a standard COM error code.

## Remarks

Minidrivers typically use the AddItemToFolder method to add an item to a parent folder item in a driver item tree. The parent folder item is pointed to by the parameter <i>pIParent</i>. The item pointed to by <i>pIParent</i> must be a folder.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me and in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | wiamindr_lh.h (include Wiamindr.h) |

## See Also

<a href="https://msdn.microsoft.com/0609e1b2-48df-413c-90bd-d7ddea26510a">IWiaDrvItem</a>



<a href="https://msdn.microsoft.com/f800427e-d6b6-4f4c-aee7-4b2b0d0aa0c4">RemoveItemFromFolder</a>