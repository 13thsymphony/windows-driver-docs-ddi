---
UID: NE:ntifs._TOKEN_TYPE
title: "_TOKEN_TYPE"
author: windows-driver-content
description: The TOKEN_TYPE enumeration type contains values that differentiate between a primary token and an impersonation token.
old-location: ifsk\token_type.htm
old-project: ifsk
ms.assetid: 2ad78d17-9baa-45cf-a620-01c2ccd14338
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PTOKEN_TYPE, PTOKEN_TYPE, PTOKEN_TYPE enumeration pointer [Installable File System Drivers], TOKEN_TYPE, TOKEN_TYPE enumeration [Installable File System Drivers], TokenImpersonation, TokenPrimary, _TOKEN_TYPE, ifsk.token_type, ntifs/PTOKEN_TYPE, ntifs/TOKEN_TYPE, ntifs/TokenImpersonation, ntifs/TokenPrimary, securitystructures_b570f2e6-2426-4c9d-8552-81131cf4bd66.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	TOKEN_TYPE
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# _TOKEN_TYPE Enumeration
The TOKEN_TYPE enumeration type contains values that differentiate between a primary token and an impersonation token.

## Syntax
````
typedef enum _TOKEN_TYPE { 
  TokenPrimary        = 1,
  TokenImpersonation  = 2
} TOKEN_TYPE, *PTOKEN_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>TokenPrimary</td>
                    <td>Indicates a primary token.</td>
                </tr>
            
                <tr>
                    <td>TokenImpersonation</td>
                    <td>Indicates an impersonation token.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntifs.h (include Ntifs.h) |

## See Also

<a href="..\ntifs\ns-ntifs-_token_statistics.md">TOKEN_STATISTICS</a>



<a href="..\ntifs\ne-ntifs-_token_information_class.md">TOKEN_INFORMATION_CLASS</a>



<a href="..\ntifs\nf-ntifs-zwsetinformationtoken.md">ZwSetInformationToken</a>



<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>



<a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>