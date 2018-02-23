---
UID: NF:mcd.ChangerClassAllocatePool
title: ChangerClassAllocatePool function
author: windows-driver-content
description: The ChangerClassAllocatePool function allocates pool memory.
old-location: storage\changerclassallocatepool.htm
old-project: storage
ms.assetid: d211bab9-4932-41c5-9b6f-528a75bb2ae4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.changerclassallocatepool, chgrclas_e1b15ece-f3e4-446f-adc4-39301fc0346f.xml, mcd/ChangerClassAllocatePool, ChangerClassAllocatePool, ChangerClassAllocatePool function [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: mcd.h
req.include-header: Mcd.h, Ntddchgr.h
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
req.lib: Mcd.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Mcd.lib
-	Mcd.dll
apiname:
-	ChangerClassAllocatePool
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---


# ChangerClassAllocatePool function
The <b>ChangerClassAllocatePool</b> function allocates pool memory.

## Syntax

````
PVOID ChangerClassAllocatePool(
  _In_ POOL_TYPE PoolType,
  _In_ ULONG     NumberOfBytes
);
````

## Parameters

`PoolType`

Indicates the type of pool memory to allocate. See <a href="..\wudfwdm\ne-wudfwdm-_pool_type.md">POOL_TYPE</a> for a list of types.

`NumberOfBytes`

Indicates number of bytes to allocate.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | mcd.h (include Mcd.h, Ntddchgr.h) |
| **Library** | Mcd.lib |

## See Also

<a href="..\wudfwdm\ne-wudfwdm-_pool_type.md">POOL_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ChangerClassAllocatePool function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>