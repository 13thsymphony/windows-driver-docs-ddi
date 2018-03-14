---
UID: NE:gnssdriver.GNSS_NI_USER_RESPONSE
title: GNSS_NI_USER_RESPONSE
author: windows-driver-content
description: This enumeration indicates the user’s response to a network initiated (NI) request, which is represented by the GNSS_NI_RESPONSE structure.
old-location: gnss\gnss_ni_user_response.htm
old-project: gnss
ms.assetid: FD4A244D-641C-46A7-8777-8F64A5400D23
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: GNSS_NI_USER_RESPONSE, GNSS_NI_USER_RESPONSE enumeration [Sensor Devices], GNSS_Ni_UserResponseAccept, GNSS_Ni_UserResponseDeny, GNSS_Ni_UserResponseTimeout, gnss.gnss_ni_user_response, gnssdriver/GNSS_NI_USER_RESPONSE, gnssdriver/GNSS_Ni_UserResponseAccept, gnssdriver/GNSS_Ni_UserResponseDeny, gnssdriver/GNSS_Ni_UserResponseTimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: gnssdriver.h
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	GNSS_NI_USER_RESPONSE
product: Windows
targetos: Windows
req.typenames: GNSS_NI_USER_RESPONSE
---

# GNSS_NI_USER_RESPONSE Enumeration
This enumeration indicates the user’s response to a network initiated (NI) request, which is represented by the <a href="..\gnssdriver\ns-gnssdriver-gnss_ni_response.md">GNSS_NI_RESPONSE</a> structure.

## Syntax
````
typedef enum  { 
  GNSS_Ni_UserResponseAccept   = 0x01,
  GNSS_Ni_UserResponseDeny     = 0x02,
  GNSS_Ni_UserResponseTimeout  = 0x03
} GNSS_NI_USER_RESPONSE;
````

## Constants

<table>
            
                <tr>
                    <td>GNSS_Ni_UserResponseAccept</td>
                    <td>Indicates that the user accepted the NI request.</td>
                </tr>
            
                <tr>
                    <td>GNSS_Ni_UserResponseDeny</td>
                    <td>Indicates that the user denied the NI request.</td>
                </tr>
            
                <tr>
                    <td>GNSS_Ni_UserResponseTimeout</td>
                    <td>Indicates that the request timed out without a user response.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | gnssdriver.h |