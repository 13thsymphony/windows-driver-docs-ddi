---
UID: NS:hbaapi.HBA_wwn
title: HBA_wwn
author: windows-driver-content
description: The HBA_wwn structure contains a 64 bit world-wide name (WWN) that uniquely identifies an HBA.
old-location: storage\hba_wwn.htm
old-project: storage
ms.assetid: 84441fde-1d66-4f76-86b7-dccd792afd0f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PHBA_WWN, HBA_WWN, HBA_WWN structure [Storage Devices], HBA_wwn, HBA_wwn structure [Storage Devices], PHBA_WWN, PHBA_WWN structure pointer [Storage Devices], hbaapi/HBA_wwn, hbaapi/PHBA_WWN, storage.hba_wwn, structs-Fibre_89c3be90-1992-4d06-9a26-c3067dc69db8.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbaapi.h
api_name:
-	HBA_WWN
product: Windows
targetos: Windows
req.typenames: HBA_WWN, *PHBA_WWN
---

# HBA_wwn structure
The HBA_wwn structure contains a 64 bit world-wide name (WWN) that uniquely identifies an HBA.

## Syntax
````
typedef struct HBA_wwn {
  HBA_UINT8 wwn[8];
} HBA_WWN, *PHBA_WWN;
````

## Members


`wwn`

Contains a 64 bit world-wide name (WWN) that uniquely identifies an HBA. .


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hbaapi.h (include Hbaapi.h) |

## See Also

<a href="..\hbaapi\ns-hbaapi-hba_mgmtinfo.md">HBA_MgmtInfo</a>



<a href="..\hbaapi\ns-hbaapi-hba_portattributes.md">HBA_PortAttributes</a>



<a href="..\hbaapi\ns-hbaapi-hba_adapterattributes.md">HBA_AdapterAttributes</a>