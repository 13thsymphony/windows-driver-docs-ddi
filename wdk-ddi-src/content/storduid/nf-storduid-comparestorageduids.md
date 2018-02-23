---
UID: NF:storduid.CompareStorageDuids
title: CompareStorageDuids function
author: windows-driver-content
description: The CompareStorageDuids routine compares two device unique identifiers (DUIDs) and reports whether they match or not.
old-location: storage\comparestorageduids.htm
old-project: storage
ms.assetid: bf66a04d-0892-4813-9615-845054526125
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: CompareStorageDuids, storduid/CompareStorageDuids, CompareStorageDuids routine [Storage Devices], storage.comparestorageduids, storertns-general_86f18b5a-ed33-48e8-b13c-76bd2422418d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storduid.h
req.include-header: Storduid.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storduid.h
apiname:
-	CompareStorageDuids
product: Windows
targetos: Windows
req.typenames: DUID_MATCH_STATUS
req.product: Windows 10 or later.
---


# CompareStorageDuids function
The <b>CompareStorageDuids</b> routine compares two device unique identifiers (DUIDs) and reports whether they match or not.

## Syntax

````
__inline DUID_MATCH_STATUS CompareStorageDuids(
  _In_ PSTORAGE_DEVICE_UNIQUE_IDENTIFIER Duid1,
  _In_ PSTORAGE_DEVICE_UNIQUE_IDENTIFIER Duid2
);
````

## Parameters

`Duid1`

A pointer to a DUID to compare with the DUID that <i>Duid2</i> points to.

`Duid2`

A pointer to a DUID to compare with the DUID that <i>Duid1</i> points to.


## Return Value

<b>CompareStorageDuids</b> returns a <a href="..\storduid\ne-storduid-_duid_match_status.md">DUID_MATCH_STATUS</a> value that indicates whether the two DUIDs matched or not, if the operation succeeds. Otherwise, this routine returns a DUID_MATCH_STATUS value that indicates the error status.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | storduid.h (include Storduid.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\storduid\ne-storduid-_duid_match_status.md">DUID_MATCH_STATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CompareStorageDuids routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>