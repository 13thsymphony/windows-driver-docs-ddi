---
UID: NS:ksi.KSCLOCKINSTANCE
title: KSCLOCKINSTANCE
author: windows-driver-content
description: "."
old-location: stream\ksclockinstance.htm
old-project: stream
ms.assetid: DC8A7CE9-7FDE-4FC9-8C71-3F3368E7E5C1
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksi/KSCLOCKINSTANCE, PKSCLOCKINSTANCE, *PKSCLOCKINSTANCE, stream.ksclockinstance, ksi/PKSCLOCKINSTANCE, KSCLOCKINSTANCE, KSCLOCKINSTANCE structure [Streaming Media Devices], PKSCLOCKINSTANCE structure pointer [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksi.h
req.include-header: 
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ksi.h
apiname:
-	KSCLOCKINSTANCE
product: Windows
targetos: Windows
req.typenames: "*PKSCLOCKINSTANCE, KSCLOCKINSTANCE"
---

# KSCLOCKINSTANCE structure


## Syntax
````
typedef struct {
  KSOBJECT_HEADER  Header;
  PKISDEFAULTCLOCK DefaultClock;
  ULONG            Reserved;
} KSCLOCKINSTANCE, *PKSCLOCKINSTANCE;
````

## Members


`DefaultClock`



`Header`



`Reserved`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksi.h |