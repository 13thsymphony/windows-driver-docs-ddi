---
UID: NE:ntddrilapitypes.RILPHONEBOOKANSOPERATION
title: RILPHONEBOOKANSOPERATION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebookansoperation.htm
old-project: netvista
ms.assetid: 29dcc5c0-0b07-49d7-b2ab-bdac7333baf7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILPHONEBOOKANSOPERATION, RILPHONEBOOKANSOPERATION enumeration [Network Drivers Starting with Windows Vista], RIL_PHONEBOOK_ANSDELETED, RIL_PHONEBOOK_ANSMODIFIED, RIL_PHONEBOOK_MAX, netvista.rilphonebookansoperation, ntddrilapitypes/RILPHONEBOOKANSOPERATION, ntddrilapitypes/RIL_PHONEBOOK_ANSDELETED, ntddrilapitypes/RIL_PHONEBOOK_ANSMODIFIED, ntddrilapitypes/RIL_PHONEBOOK_MAX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILPHONEBOOKANSOPERATION
product: Windows
targetos: Windows
req.typenames: RILPHONEBOOKANSOPERATION
---

# RILPHONEBOOKANSOPERATION Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILPHONEBOOKANSOPERATION { 
  RIL_PHONEBOOK_ANSMODIFIED,
  RIL_PHONEBOOK_ANSDELETED,
  RIL_PHONEBOOK_MAX
} RILPHONEBOOKANSOPERATION;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PHONEBOOK_ANSADDED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PHONEBOOK_ANSDELETED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PHONEBOOK_ANSMODIFIED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PHONEBOOK_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |