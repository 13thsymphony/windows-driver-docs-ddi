---
UID: NF:wdtf.IWDTFTargets2.GetInterfacesIfExist
title: IWDTFTargets2::GetInterfacesIfExist method
author: windows-driver-content
description: Returns a collection of actions that support the interface - one IWDTFAction2 for each item that has one.
old-location: dtf\iwdtftargets2_getinterfacesifexist.htm
old-project: dtf
ms.assetid: 5ec2e981-87ee-4ebe-ae60-c5acae2c073e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetInterfacesIfExist method [Windows Device Testing Framework], GetInterfacesIfExist method [Windows Device Testing Framework], IWDTFTargets2 interface, GetInterfacesIfExist,IWDTFTargets2.GetInterfacesIfExist, IWDTFTargets2, IWDTFTargets2 interface [Windows Device Testing Framework], GetInterfacesIfExist method, IWDTFTargets2::GetInterfacesIfExist, Microsoft.WDTF.IWDTFTargets2.GetInterfacesIfExist, Microsoft::WDTF::IWDTFTargets2::GetInterfacesIfExist, dtf.iwdtftargets2_getinterfacesifexist, wdtf/IWDTFTargets2::GetInterfacesIfExist
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
-	IWDTFTargets2.GetInterfacesIfExist
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# GetInterfacesIfExist method
Returns a collection of actions that support the interface - one <a href="..\wdtf\nn-wdtf-iwdtfaction2.md">IWDTFAction2</a> for each item
that has one.

## Syntax

````
HRESULT GetInterfacesIfExist(
  [in]           BSTR          ProgID,
  [in, optional] VARIANT       MoreTargets,
  [in, optional] VARIANT       MonikerSuffix,
  [out, retval]  IWDTFActions2 **ppInterface
);
````

## Parameters

`WDTFInterfaceName`



`MoreTargets`

Optional extra arguments that you can use to 
define additional targets to attach to the returned interface. 

This parameter is not 
currently implemented. Set <i>MoreTargets </i>to a <b>VARIANT</b> 
that contains <b>VT_EMPTY</b>.

`MonikerSuffix`

An optional moniker that defines more options about how 
the interface should be instantiated. 

This parameter is not yet implemented. 
Set <i>MonikerSuffix </i>to a <b>VARIANT</b> that 
contains <b>VT_EMPTY</b>.

`ppInterface`

The address of a variable that will receive the 
collection of actions.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

This method will succeed even if one or more of the collection members do not return an action.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |

## See Also

<a href="..\wdtf\nn-wdtf-iwdtftargets2.md">IWDTFTargets2</a>