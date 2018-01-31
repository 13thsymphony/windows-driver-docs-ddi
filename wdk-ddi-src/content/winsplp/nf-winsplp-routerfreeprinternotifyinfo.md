---
UID : NF:winsplp.RouterFreePrinterNotifyInfo
title : RouterFreePrinterNotifyInfo function
author : windows-driver-content
description : The print spooler's RouterFreePrinterNotifyInfo function deallocates a specified PRINTER_NOTIFY_INFO structure and its associated PRINTER_NOTIFY_INFO_DATA structure array.
old-location : print\routerfreeprinternotifyinfo.htm
old-project : print
ms.assetid : 11beef0b-061a-4d73-b723-d0214f479503
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : spoolfnc_7ae0296f-8bfe-4ee3-b621-1d1582deafdf.xml, winsplp/RouterFreePrinterNotifyInfo, RouterFreePrinterNotifyInfo, print.routerfreeprinternotifyinfo, RouterFreePrinterNotifyInfo function [Print Devices]
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
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Spoolss.lib
req.dll : Spoolss.dll
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NOTIFICATION_CONFIG_FLAGS
req.product : Windows 10 or later.
---


# RouterFreePrinterNotifyInfo function
The print spooler's <code>RouterFreePrinterNotifyInfo</code> function deallocates a specified PRINTER_NOTIFY_INFO structure and its associated PRINTER_NOTIFY_INFO_DATA structure array. (These structures are described in the Microsoft Windows SDK documentation.)

## Syntax

````
BOOL RouterFreePrinterNotifyInfo(
  _In_opt_ PPRINTER_NOTIFY_INFO pInfo
);
````

## Parameters

`pInfo`

Caller-supplied pointer to a PRINTER_NOTIFY_INFO structure (described in the Windows SDK documentation).


## Return Value

If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>.

## Remarks

A print provider's <a href="https://msdn.microsoft.com/library/windows/hardware/ff561930">RefreshPrinterChangeNotification</a> function should call <code>RouterFreePrinterNotifyInfo</code> to deallocate structures previously allocated by <a href="..\winsplp\nf-winsplp-routerallocprinternotifyinfo.md">RouterAllocPrinterNotifyInfo</a>, but only if <b>RefreshPrinterChangeNotification</b> encounters a error. If <b>RefreshPrinterChangeNotification</b> succeeds, you should assume that the client application will deallocate the structures.

Besides deallocating the specified PRINTER_NOTIFY_INFO structure and its associated PRINTER_NOTIFY_INFO_DATA structure array, the function also deallocates buffer space pointed to by <i>pBuf</i> in any element of the PRINTER_NOTIFY_INFO_DATA structure array.

For additional information, see <a href="https://msdn.microsoft.com/e75c6f89-9cef-4900-af89-edf1f7f786c7">Supporting Printer Change Notifications</a>.

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

<a href="..\winsplp\nf-winsplp-routerallocprinternotifyinfo.md">RouterAllocPrinterNotifyInfo</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561930">RefreshPrinterChangeNotification</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20RouterFreePrinterNotifyInfo function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>