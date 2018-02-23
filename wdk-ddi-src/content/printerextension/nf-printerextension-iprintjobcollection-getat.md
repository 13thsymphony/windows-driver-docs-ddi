---
UID: NF:printerextension.IPrintJobCollection.GetAt
title: IPrintJobCollection::GetAt method
author: windows-driver-content
description: Gets a pointer to an IPrintJob object.
old-location: print\iprintjobcollection_getat.htm
old-project: print
ms.assetid: B920E5D1-D565-4626-A15E-8500DFFBC9FF
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: GetAt, GetAt method [Print Devices], IPrintJobCollection, print.iprintjobcollection_getat, IPrintJobCollection interface [Print Devices], GetAt method, printerextension/IPrintJobCollection::GetAt, GetAt method [Print Devices], IPrintJobCollection interface, IPrintJobCollection::GetAt
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrintJobCollection.GetAt
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# GetAt method
Gets a pointer to an <a href="..\printerextension\nn-printerextension-iprintjob.md">IPrintJob</a> object.

## Syntax

````
HRESULT GetAt(
  [in]          ULONG     ulIndex,
  [out, retval] IPrintJob **ppJob
);
````

## Parameters

`ulIndex`

Index of the <b>IPrintJob</b> object within the collection.

`ppJob`

Pointer to an <b>IPrintJob</b> object.


## Return Value

Returns an <b>HRESULT</b> value. If the method call was not successful, it returns the appropriate <b>HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprintjobcollection.md">IPrintJobCollection</a>



<a href="..\printerextension\nn-printerextension-iprintjob.md">IPrintJob</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintJobCollection::GetAt method%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>