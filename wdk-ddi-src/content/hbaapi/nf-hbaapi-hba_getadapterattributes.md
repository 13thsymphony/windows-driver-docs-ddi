---
UID: NF:hbaapi.HBA_GetAdapterAttributes
title: HBA_GetAdapterAttributes function
author: windows-driver-content
description: The HBA_GetAdapterAttributes routine retrieves the attributes for an HBA.
old-location: storage\hba_getadapterattributes.htm
old-project: storage
ms.assetid: a172f53c-9993-4d52-ae3f-35a8ab5745f6
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: fibreHBA_rtns_f7675f0c-2f71-428e-871b-90c51a1b5bc4.xml, storage.hba_getadapterattributes, HBA_GetAdapterAttributes routine [Storage Devices], HBA_GetAdapterAttributes, hbaapi/HBA_GetAdapterAttributes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Desktop
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
req.lib: Hbaapi.lib
req.dll: Hbaapi.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Hbaapi.dll
apiname:
-	HBA_GetAdapterAttributes
product: Windows
targetos: Windows
req.typenames: HBA_WWNTYPE
---


# HBA_GetAdapterAttributes function
The <b>HBA_GetAdapterAttributes</b> routine retrieves the attributes for an HBA.

## Syntax

````
HBA_STATUS HBA_API HBA_GetAdapterAttributes(
  _In_  HBA_HANDLE            HbaHandle,
  _Out_ HBA_ADAPTERATTRIBUTES *HbaAdapterAttributes
);
````

## Parameters

`Handle`

TBD

`HbaAttributes`

TBD


## Return Value

The <b>HBA_GetAdapterAttributes</b> routine returns a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the status of the HBA.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | hbaapi.h (include Hbaapi.h) |
| **Library** | Hbaapi.lib |
| **DLL** | Hbaapi.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="..\hbaapi\ns-hbaapi-hba_adapterattributes.md">HBA_AdapterAttributes</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_GetAdapterAttributes routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>