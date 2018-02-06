---
UID: NS:hbapiwmi._MS_SMHBA_PORTLUN
title: "_MS_SMHBA_PORTLUN"
author: windows-driver-content
description: The MS_SMHBA_PORTLUN structure reports target LUN information that is associated with a port.
old-location: storage\ms_smhba_portlun.htm
old-project: storage
ms.assetid: cf62685f-7b4d-4671-a755-d59a593bf5d6
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: hbapiwmi/MS_SMHBA_PORTLUN, hbapiwmi/PMS_SMHBA_PORTLUN, PMS_SMHBA_PORTLUN, MS_SMHBA_PORTLUN structure [Storage Devices], PMS_SMHBA_PORTLUN structure pointer [Storage Devices], *PMS_SMHBA_PORTLUN, _MS_SMHBA_PORTLUN, structs-Fibre_a0363ae3-80ce-4efd-8409-826d1810190c.xml, storage.ms_smhba_portlun, MS_SMHBA_PORTLUN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
-	hbapiwmi.h
apiname:
-	MS_SMHBA_PORTLUN
product: Windows
targetos: Windows
req.typenames: "*PMS_SMHBA_PORTLUN, MS_SMHBA_PORTLUN"
---

# _MS_SMHBA_PORTLUN structure
The MS_SMHBA_PORTLUN structure reports target LUN information that is associated with a port.

## Syntax
````
typedef struct _MS_SMHBA_PORTLUN {
  UCHAR     PortWWN[8];
  UCHAR     domainPortWWN[8];
  ULONGLONG TargetLun;
} MS_SMHBA_PORTLUN, *PMS_SMHBA_PORTLUN;
````

## Members


`domainPortWWN`

A worldwide name that specifies the SAS domain worldwide name of the local port.

`PortWWN`

The worldwide name of the local port whose events the WMI client will receive.

`TargetLun`

The target LUN number.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbapiwmi.h (include Hbapiwmi.h) |