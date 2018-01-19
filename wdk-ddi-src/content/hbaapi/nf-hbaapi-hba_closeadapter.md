---
UID : NF:hbaapi.HBA_CloseAdapter
title : HBA_CloseAdapter function
author : windows-driver-content
description : The HBA_CloseAdapter routine releases system resources associated with the indicated open HBA handle.
old-location : storage\hba_closeadapter.htm
old-project : storage
ms.assetid : 404c7f82-02dd-4145-91e3-8820f6cbf781
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : HBA_CloseAdapter
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : hbaapi.h
req.include-header : Hbaapi.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : HBA_CloseAdapter
req.alt-loc : Hbaapi.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Hbaapi.lib
req.dll : Hbaapi.dll
req.irql : 
req.typenames : HBA_WWNTYPE
---


# HBA_CloseAdapter function
The <b>HBA_CloseAdapter</b> routine releases system resources associated with the indicated open HBA handle.

## Syntax

````
void HBA_API HBA_CloseAdapter(
  _In_ HBA_HANDLE HbaHandle
);
````

## Parameters

`handle`




## Return Value

None.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | hbaapi.h (include Hbaapi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\hbaapi\nf-hbaapi-hba_openadapter.md">HBA_OpenAdapter</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_CloseAdapter routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>