---
UID: NF:wudfddi.IWDFNamedPropertyStore.GetNameAt
title: IWDFNamedPropertyStore::GetNameAt method
author: windows-driver-content
description: The GetNameAt method retrieves the name of a property.
old-location: wdf\iwdfnamedpropertystore_getnameat.htm
old-project: wdf
ms.assetid: f6ebf45b-b411-4684-b430-0b17a56ec0c0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetNameAt method, GetNameAt method, IWDFNamedPropertyStore interface, GetNameAt,IWDFNamedPropertyStore.GetNameAt, IWDFNamedPropertyStore, IWDFNamedPropertyStore interface, GetNameAt method, IWDFNamedPropertyStore::GetNameAt, UMDFPropertyStoreObjectRef_d7568b53-9673-4344-bbbc-100fc19aaba5.xml, umdf.iwdfnamedpropertystore_getnameat, wdf.iwdfnamedpropertystore_getnameat, wudfddi/IWDFNamedPropertyStore::GetNameAt
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFNamedPropertyStore.GetNameAt
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFNamedPropertyStore::GetNameAt method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetNameAt</b> method retrieves the name of a property.

## Syntax

```
HRESULT GetNameAt(
  DWORD iProp,
  PWSTR *ppwszName
);
```

## Parameters

`iProp`

The zero-based index of the property that <b>GetNameAt</b> retrieves the name from.

`ppwszName`

A pointer to a variable that receives a pointer to a <b>NULL</b>-terminated string that contains the name of the property.


## Return Value

<b>GetNameAt</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## Remarks

For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-the-registry-in-umdf-1-x-drivers">Using the Registry in UMDF-based Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560164">IWDFNamedPropertyStore</a>