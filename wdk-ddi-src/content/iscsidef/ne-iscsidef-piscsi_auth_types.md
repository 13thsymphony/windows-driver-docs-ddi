---
UID: NE:iscsidef.PISCSI_AUTH_TYPES
title: "*PISCSI_AUTH_TYPES"
author: windows-driver-content
description: The ISCSI_AUTH_TYPES enumeration indicates the type of authentication method that is used to establish a logon connection.
old-location: storage\iscsi_auth_types.htm
old-project: storage
ms.assetid: b1d38829-53bc-42a5-acaf-c1ad89b8b563
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "*PISCSI_AUTH_TYPES, iscsidef/PISCSI_AUTH_TYPES, ISCSI_NO_AUTH_TYPE, iscsidef/ISCSI_NO_AUTH_TYPE, ISCSI_AUTH_TYPES, iscsidef/ISCSI_CHAP_AUTH_TYPE, PISCSI_AUTH_TYPES, ISCSI_CHAP_AUTH_TYPE, PISCSI_AUTH_TYPES enumeration pointer [Storage Devices], iscsidef/ISCSI_MUTUAL_CHAP_AUTH_TYPE, iscsidef/ISCSI_AUTH_TYPES, ISCSI_AUTH_TYPES enumeration [Storage Devices], storage.iscsi_auth_types, structs-iSCSI_a55ac905-6962-416f-a197-778a24eae524.xml, ISCSI_MUTUAL_CHAP_AUTH_TYPE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: iscsidef.h
req.include-header: Iscsidef.h
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
-	iscsidef.h
apiname:
-	ISCSI_AUTH_TYPES
product: Windows
targetos: Windows
req.typenames: ISCSI_AUTH_TYPES, *PISCSI_AUTH_TYPES
---

# *PISCSI_AUTH_TYPES Enumeration
The ISCSI_AUTH_TYPES enumeration indicates the type of authentication method that is used to establish a logon connection.

## Syntax
````
typedef enum  { 
  ISCSI_NO_AUTH_TYPE           = 0,
  ISCSI_CHAP_AUTH_TYPE         = 1,
  ISCSI_MUTUAL_CHAP_AUTH_TYPE  = 2
} ISCSI_AUTH_TYPES, *PISCSI_AUTH_TYPES;
````

## Constants

<table>
            
                <tr>
                    <td>ISCSI_CHAP_AUTH_TYPE</td>
                    <td>Challenge handshake authentication protocol (CHAP).</td>
                </tr>
            
                <tr>
                    <td>ISCSI_MUTUAL_CHAP_AUTH_TYPE</td>
                    <td>Mutual (2-way) CHAP authentication.</td>
                </tr>
            
                <tr>
                    <td>ISCSI_NO_AUTH_TYPE</td>
                    <td>No authentication type was specified.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iscsidef.h (include Iscsidef.h) |