---
UID: NF.wiamindr_lh.IWiaDrvItem.GetFullItemName
title: IWiaDrvItem::GetFullItemName
author: windows-driver-content
description: The IWiaDrvItem::GetFullItemName method gets the item's full name, including path information.
old-location: image\iwiadrvitem_getfullitemname.htm
old-project: image
ms.assetid: 810faf49-faa9-45f2-af94-af576f4c1075
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: IWiaDrvItem, GetFullItemName, IWiaDrvItem::GetFullItemName
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
req.alt-api: IWiaDrvItem.GetFullItemName
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

# IWiaDrvItem::GetFullItemName method



## -description
<p>The <b>IWiaDrvItem::GetFullItemName</b> method gets the item's full name, including path information.</p>


## -syntax

````
HRESULT GetFullItemName(
  [out, optional] BSTR *pbstrFullItemName
);
````


## -parameters
<dl>

### -param <i>pbstrFullItemName</i> [out, optional]

<dd>
<p>Points to a memory location that will receive the address of a string containing the item's full name. </p>
</dd>
</dl>

## -returns
<p>If the method succeeds, it stores a pointer to the item's full name, including path information, in <i>pbstrFullItemName</i> and returns S_OK. If the method fails to allocate the string due to insufficient memory, it returns E_OUTOFMEMORY. If the parameter <i>pbstrFullItemName</i> is invalid, the method returns E_INVALIDARG. If the method fails for another reason, it returns a standard COM error code.</p>

## -remarks
<p>If there is enough memory available, this method allocates a string containing the current item's full name including path information. The method returns a pointer to the string in <i>pbstrFullItemName</i>. The minidriver must deallocate the memory used by the string by calling the <b>SysFreeString</b> function, which is documented in the Microsoft Windows SDK documentation. </p>

<p>The name returned in <i>pbstrFullItemName </i>is the name associated with the item when the item was first created by the driver services library function <a href="https://msdn.microsoft.com/library/windows/hardware/ff549160">wiasCreateDrvItem</a>.</p>

<p>If there is enough memory available, this method allocates a string containing the current item's full name including path information. The method returns a pointer to the string in <i>pbstrFullItemName</i>. The minidriver must deallocate the memory used by the string by calling the <b>SysFreeString</b> function, which is documented in the Microsoft Windows SDK documentation. </p>

<p>The name returned in <i>pbstrFullItemName </i>is the name associated with the item when the item was first created by the driver services library function <a href="https://msdn.microsoft.com/library/windows/hardware/ff549160">wiasCreateDrvItem</a>.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549160">wiasCreateDrvItem</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaDrvItem::GetFullItemName method%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
