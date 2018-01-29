---
UID : NF:dbgeng.IDebugPlmClient3.TerminatePlmPackageWide
title : IDebugPlmClient3::TerminatePlmPackageWide method
author : windows-driver-content
description : Ends a Process Lifecycle Management (PLM) package.
old-location : debugger\idebugplmclient3_terminateplmpackagewide.htm
old-project : debugger
ms.assetid : EBEEF2C7-AD2E-4BE5-B20C-D4E148F1454C
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : TerminatePlmPackageWide method [Windows Debugging], TerminatePlmPackageWide method [Windows Debugging], IDebugPlmClient3 interface, dbgeng/IDebugPlmClient3::TerminatePlmPackageWide, debugger.idebugplmclient3_terminateplmpackagewide, IDebugPlmClient3::TerminatePlmPackageWide, IDebugPlmClient3 interface [Windows Debugging], TerminatePlmPackageWide method, IDebugPlmClient3, TerminatePlmPackageWide
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : dbgeng.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# TerminatePlmPackageWide method
Ends a Process Lifecycle Management (PLM) package.

## Syntax

````
HRESULT TerminatePlmPackageWide(
  [in] ULONG64 Server,
  [in] PCWSTR  PackageFullName
);
````

## Parameters

`Server`

The server of the package.

`PackageFullName`

A pointer to the package name.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugplmclient3.md">IDebugPlmClient3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugPlmClient3::TerminatePlmPackageWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>