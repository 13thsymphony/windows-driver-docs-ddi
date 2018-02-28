---
UID: NF:wiamindr_lh.IWiaDrvItem.GetFullItemName
title: IWiaDrvItem::GetFullItemName method
author: windows-driver-content
description: The IWiaDrvItem::GetFullItemName method gets the item's full name, including path information.
old-location: image\iwiadrvitem_getfullitemname.htm
old-project: image
ms.assetid: 810faf49-faa9-45f2-af94-af576f4c1075
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: DrvItem_1b166476-d17a-4953-9c73-6e3d7c9cd0f9.xml, GetFullItemName method [Imaging Devices], GetFullItemName method [Imaging Devices], IWiaDrvItem interface, GetFullItemName,IWiaDrvItem.GetFullItemName, IWiaDrvItem, IWiaDrvItem interface [Imaging Devices], GetFullItemName method, IWiaDrvItem::GetFullItemName, image.iwiadrvitem_getfullitemname, wiamindr_lh/IWiaDrvItem::GetFullItemName
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
-	IWiaDrvItem.GetFullItemName
product: Windows
targetos: Windows
req.typenames: SCANWINDOW, *PSCANWINDOW
req.product: Windows 10 or later.
---


# GetFullItemName method
The <b>IWiaDrvItem::GetFullItemName</b> method gets the item's full name, including path information.

## Syntax

````
HRESULT GetFullItemName(
  [out, optional] BSTR *pbstrFullItemName
);
````

## Parameters

`__MIDL__IWiaDrvItem0002`




## Return Value

If the method succeeds, it stores a pointer to the item's full name, including path information, in <i>pbstrFullItemName</i> and returns S_OK. If the method fails to allocate the string due to insufficient memory, it returns E_OUTOFMEMORY. If the parameter <i>pbstrFullItemName</i> is invalid, the method returns E_INVALIDARG. If the method fails for another reason, it returns a standard COM error code.

## Remarks

If there is enough memory available, this method allocates a string containing the current item's full name including path information. The method returns a pointer to the string in <i>pbstrFullItemName</i>. The minidriver must deallocate the memory used by the string by calling the <b>SysFreeString</b> function, which is documented in the Microsoft Windows SDK documentation. 

The name returned in <i>pbstrFullItemName </i>is the name associated with the item when the item was first created by the driver services library function <a href="..\wiamdef\nf-wiamdef-wiascreatedrvitem.md">wiasCreateDrvItem</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me and in Windows XP and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | wiamindr_lh.h (include Wiamindr.h) |
| **Library** | wiamindr_lh.h |

## See Also

<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiadrvitem.md">IWiaDrvItem</a>



<a href="..\wiamdef\nf-wiamdef-wiascreatedrvitem.md">wiasCreateDrvItem</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaDrvItem::GetFullItemName method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>