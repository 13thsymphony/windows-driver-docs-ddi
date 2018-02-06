---
UID: NF:printoem.OEMUpgradeRegistry
title: OEMUpgradeRegistry function
author: windows-driver-content
description: OEMUpgradeRegistry function
old-location: print\oemupgraderegistry.htm
old-project: print
ms.assetid: 780ae330-907e-4e77-a5f9-cb44811f289f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: OEMUpgradeRegistry, print.oemupgraderegistry, print_obsoletefunctions_5837e384-9879-4909-8dfa-f3c74486bde0.xml, printoem/OEMUpgradeRegistry, OEMUpgradeRegistry function [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	OEMUpgradeRegistry
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMUpgradeRegistry function


## Syntax

````
BOOL APIENTRY OEMUpgradeRegistry(
   DWORD                         dwLevel,
   PBYTE                         pDriverUpgradeInfo,
   PFN_DrvUpgradeRegistrySetting pfnUpgrade
);
````

## Parameters

`dwLevel`



`pDriverUpgradeInfo`



`pfnUpgrade`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548652">DrvUpgradeRegistrySetting</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20OEMUpgradeRegistry function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>