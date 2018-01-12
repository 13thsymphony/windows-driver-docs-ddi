---
UID: NF:wiautil.CWiauPropertyList.SendToWia
title: CWiauPropertyList::SendToWia method
author: windows-driver-content
description: The CWiauPropertyList::SendToWia method calls the WIA service to define all of the properties currently contained in the property list object.
old-location: image\cwiaupropertylist_sendtowia.htm
old-project: image
ms.assetid: 2f7d6975-4c90-4351-bf68-89786bafcc8e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: CWiauPropertyList, CWiauPropertyList::SendToWia, SendToWia
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CWiauPropertyList.SendToWia
req.alt-loc: Wiautil.h
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
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# CWiauPropertyList::SendToWia method



## -description
The <b>CWiauPropertyList::SendToWia</b> method calls the WIA service to define all of the properties currently contained in the property list object. 



## -syntax

````
HRESULT SendToWia(
       BYTE   *pWiasContext
);
````


## -parameters

### -param pWiasContext 

Pointer to a WIA item context that previously was passed in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544989">IWiaMiniDrv::drvInitItemProperties</a> method.


## -returns
On success, the <b>CWiauPropertyList::SendToWia</b> method returns S_OK. If the property list contains no properties, the method returns E_FAIL. 


## -remarks
The <b>CWiauPropertyList::SendToWia</b> method should be called only after all properties have been defined and their values set.


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
Available in Windows XP and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wiautil.h (include Wiautil.h or Wiamindr.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544989">IWiaMiniDrv::drvInitItemProperties</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20CWiauPropertyList::SendToWia method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

