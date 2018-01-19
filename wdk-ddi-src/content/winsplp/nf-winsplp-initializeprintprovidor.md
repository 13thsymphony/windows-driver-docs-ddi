---
UID : NF:winsplp.InitializePrintProvidor
title : InitializePrintProvidor function
author : windows-driver-content
description : Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated.
old-location : print\initializeprintprovidor.htm
old-project : print
ms.assetid : 54a5009d-9893-4766-b9fd-7e7474b55949
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : InitializePrintProvidor
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : winsplp.h
req.include-header : Winsplp.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : InitializePrintProvidor
req.alt-loc : winsplp.h
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
req.typenames : NOTIFICATION_CONFIG_FLAGS
req.product : Windows 10 or later.
---


# InitializePrintProvidor function


## Syntax

````
BOOL InitializePrintProvidor(
  _Out_    LPPRINTPROVIDOR pPrintProvidor,
  _In_     DWORD           cbPrintProvidor,
  _In_opt_ LPWSTR          pFullRegistryPath
);
````

## Parameters

`pPrintProvidor`

Caller-supplied address of a <a href="..\winsplp\ns-winsplp-_printprovidor.md">PRINTPROVIDOR</a> structure, to be filled in by the print provider.

`cbPrintProvidor`

Caller-supplied size, in bytes, of the PRINTPROVIDOR structure pointed to by <i>pPrintProvidor</i>.

`pFullRegistryPath`

Caller-supplied pointer to a string representing the full registry path to the provider's registry entry.


## Return Value

If the operation succeeds, the function should return <b>TRUE</b>. Otherwise the function should return <b>FALSE</b>.

## Remarks

Print providers are required to define an <b>InitializePrintProvidor</b> function, which is the first function called by the spooler after the provider has been loaded. The function must fill the supplied <a href="..\winsplp\ns-winsplp-_printprovidor.md">PRINTPROVIDOR</a> structure with pointers to the provider's defined functions (see <a href="https://msdn.microsoft.com/4fae4b69-ed4b-47b6-b6e8-41733aed51a5">Functions Defined by Print Providers</a>). The function can also perform other provider-specific initialization operations.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | winsplp.h (include Winsplp.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\winsplp\ns-winsplp-_printprovidor.md">PRINTPROVIDOR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20InitializePrintProvidor function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>