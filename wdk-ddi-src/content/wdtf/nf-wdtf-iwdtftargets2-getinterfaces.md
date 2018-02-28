---
UID: NF:wdtf.IWDTFTargets2.GetInterfaces
title: IWDTFTargets2::GetInterfaces method
author: windows-driver-content
description: Returns a collection of actions that support the interface - one IWDTFAction2 for each item that has one.
old-location: dtf\iwdtftargets2_getinterfaces.htm
old-project: dtf
ms.assetid: 8e9735b2-23d3-4fe6-8184-31e7707b6400
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetInterfaces method [Windows Device Testing Framework], GetInterfaces method [Windows Device Testing Framework], IWDTFTargets2 interface, GetInterfaces,IWDTFTargets2.GetInterfaces, IWDTFTargets2, IWDTFTargets2 interface [Windows Device Testing Framework], GetInterfaces method, IWDTFTargets2::GetInterfaces, Microsoft.WDTF.IWDTFTargets2.GetInterfaces, Microsoft::WDTF::IWDTFTargets2::GetInterfaces, dtf.iwdtftargets2_getinterfaces, wdtf/IWDTFTargets2::GetInterfaces
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
req.lib: wdtf.h
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
-	IWDTFTargets2.GetInterfaces
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# GetInterfaces method
Returns a collection of actions that support the interface - one <a href="..\wdtf\nn-wdtf-iwdtfaction2.md">IWDTFAction2</a> for each item
that has one.

## Syntax

````
HRESULT GetInterfaces(
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

If any items in the collection fail to return an action, this method fails.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |
| **Library** | wdtf.h |

## See Also

<a href="..\wdtf\nn-wdtf-iwdtftargets2.md">IWDTFTargets2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFTargets2::GetInterfaces method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>