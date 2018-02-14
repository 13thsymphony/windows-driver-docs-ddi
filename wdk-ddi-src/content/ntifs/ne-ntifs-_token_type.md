---
UID: NE:ntifs._TOKEN_TYPE
title: "_TOKEN_TYPE"
author: windows-driver-content
description: The TOKEN_TYPE enumeration type contains values that differentiate between a primary token and an impersonation token.
old-location: ifsk\token_type.htm
old-project: ifsk
ms.assetid: 2ad78d17-9baa-45cf-a620-01c2ccd14338
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: TokenPrimary, ntifs/TokenPrimary, ntifs/TokenImpersonation, securitystructures_b570f2e6-2426-4c9d-8552-81131cf4bd66.xml, PTOKEN_TYPE, TokenImpersonation, TOKEN_TYPE enumeration [Installable File System Drivers], ifsk.token_type, ntifs/PTOKEN_TYPE, ntifs/TOKEN_TYPE, *PTOKEN_TYPE, TOKEN_TYPE, _TOKEN_TYPE, PTOKEN_TYPE enumeration pointer [Installable File System Drivers]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
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
                    <td>TokenImpersonation</td>
                    <td>Indicates an impersonation token.</td>
                </tr>
            
                <tr>
                    <td>TokenPrimary</td>
                    <td>Indicates a primary token.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntifs.h (include Ntifs.h) |

    ## See Also

        <a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>



<a href="..\ntifs\ne-ntifs-_token_information_class.md">TOKEN_INFORMATION_CLASS</a>



<a href="..\ntifs\ns-ntifs-_token_statistics.md">TOKEN_STATISTICS</a>



<a href="..\ntifs\nf-ntifs-zwsetinformationtoken.md">ZwSetInformationToken</a>



<a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_TYPE enumeration%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>