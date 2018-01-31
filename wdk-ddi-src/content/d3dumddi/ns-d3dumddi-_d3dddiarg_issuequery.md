---
UID : NS:d3dumddi._D3DDDIARG_ISSUEQUERY
title : "_D3DDDIARG_ISSUEQUERY"
author : windows-driver-content
description : The D3DDDIARG_ISSUEQUERY structure describes how to process a query that was created by the CreateQuery function.
old-location : display\d3dddiarg_issuequery.htm
old-project : display
ms.assetid : af52d1a3-b537-48d2-ab57-3f798ec83c98
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.d3dddiarg_issuequery, D3DDDIARG_ISSUEQUERY structure [Display Devices], UMDisplayDriver_param_Structs_3fb59dbc-e5de-4d14-9d4b-25934e4e3ded.xml, _D3DDDIARG_ISSUEQUERY, D3DDDIARG_ISSUEQUERY, d3dumddi/D3DDDIARG_ISSUEQUERY
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DDDIARG_ISSUEQUERY
---

# _D3DDDIARG_ISSUEQUERY structure
The D3DDDIARG_ISSUEQUERY structure describes how to process a query that was created by the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createquery.md">CreateQuery</a> function.

## Syntax
````
typedef struct _D3DDDIARG_ISSUEQUERY {
  HANDLE                 hQuery;
  D3DDDI_ISSUEQUERYFLAGS Flags;
} D3DDDIARG_ISSUEQUERY;
````

## Members


`Flags`

[in] A <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_issuequeryflags.md">D3DDDI_ISSUEQUERYFLAGS</a> structure that identifies the type of query to issue. The driver can ignore query requests with <b>Flags</b> set to 0. 

For many query types, start query is never specified (that is, the <b>Begin</b> bit-field flag is never set for many query types). For more information about whether the <b>Begin</b> bit-field flag is set for a query type, see the <b>QueryType</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createquery.md">D3DDDIARG_CREATEQUERY</a> structure.

`hQuery`

[in] The handle to the query that was created by the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createquery.md">CreateQuery</a> function.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_issuequeryflags.md">D3DDDI_ISSUEQUERYFLAGS</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createquery.md">CreateQuery</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_issuequery.md">IssueQuery</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_ISSUEQUERY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>