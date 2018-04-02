---
UID: NF:wdtf.IWDTFTarget2.HasInterface
title: IWDTFTarget2::HasInterface method
author: windows-driver-content
description: Determines whether the target supports a given interface.
old-location: dtf\iwdtftarget2_hasinterface.htm
old-project: dtf
ms.assetid: 91641007-57c0-4e55-8ac1-9a5cc62b80b0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HasInterface method [Windows Device Testing Framework], HasInterface method [Windows Device Testing Framework], IWDTFTarget2 interface, HasInterface,IWDTFTarget2.HasInterface, IWDTFTarget2, IWDTFTarget2 interface [Windows Device Testing Framework], HasInterface method, IWDTFTarget2::HasInterface, Microsoft.WDTF.IWDTFTarget2.HasInterface, Microsoft::WDTF::IWDTFTarget2::HasInterface, dtf.iwdtftarget2_hasinterface, wdtf/IWDTFTarget2::HasInterface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
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
-	WDTF.Interop.metadata_dll.dll
api_name:
-	IWDTFTarget2.HasInterface
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFTarget2::HasInterface method
Determines whether the target supports a given interface.

## Syntax

```
HRESULT HasInterface(
  BSTR         WDTFInterfaceName,
  VARIANT      Args,
  VARIANT      MonikerSuffix,
  VARIANT_BOOL *pResult
);
```

## Parameters

`WDTFInterfaceName`



`Args`



`MonikerSuffix`

An optional moniker that defines more options about how 
the interface should be instantiated. 

This parameter is not yet implemented. 
Set <i>MonikerSuffix </i>to a <b>VARIANT</b> that 
contains <b>VT_EMPTY</b>.

`pResult`

True if the target supports the interface; otherwise false.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439367">IWDTFTarget2</a>