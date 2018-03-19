---
UID: NF:wiautil.CWiauPropertyList.SendToWia
title: CWiauPropertyList::SendToWia method
author: windows-driver-content
description: The CWiauPropertyList::SendToWia method calls the WIA service to define all of the properties currently contained in the property list object.
old-location: image\cwiaupropertylist_sendtowia.htm
old-project: image
ms.assetid: 2f7d6975-4c90-4351-bf68-89786bafcc8e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: CWiauPropertyList, CWiauPropertyList interface [Imaging Devices], SendToWia method, CWiauPropertyList::SendToWia, SendToWia method [Imaging Devices], SendToWia method [Imaging Devices], CWiauPropertyList interface, SendToWia,CWiauPropertyList.SendToWia, image.cwiaupropertylist_sendtowia, wiauFncs_d77b66a2-1c98-4608-9269-ab1e09a98405.xml, wiautil/CWiauPropertyList::SendToWia
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
-	Wiautil.h
api_name:
-	CWiauPropertyList.SendToWia
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---


# SendToWia method
The <b>CWiauPropertyList::SendToWia</b> method calls the WIA service to define all of the properties currently contained in the property list object.

## Syntax

````
HRESULT SendToWia(
       BYTE   *pWiasContext
);
````

## Parameters

`pWiasContext`

Pointer to a WIA item context that previously was passed in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544989">IWiaMiniDrv::drvInitItemProperties</a> method.


## Return Value

On success, the <b>CWiauPropertyList::SendToWia</b> method returns S_OK. If the property list contains no properties, the method returns E_FAIL.

## Remarks

The <b>CWiauPropertyList::SendToWia</b> method should be called only after all properties have been defined and their values set.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later.  |
| **Target Platform** | Desktop |
| **Header** | wiautil.h (include Wiautil.h, Wiamindr.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544989">IWiaMiniDrv::drvInitItemProperties</a>



<a href="..\wiautil\nl-wiautil-cwiaupropertylist.md">CWiauPropertyList</a>