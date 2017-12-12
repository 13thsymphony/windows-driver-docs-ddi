---
UID: NF.winsplp.SpoolerRefreshPrinterChangeNotification
title: SpoolerRefreshPrinterChangeNotification function
author: windows-driver-content
description: .
old-location: print\spoolerrefreshprinterchangenotification.htm
old-project: print
ms.assetid: 86D8D605-3620-4F43-B4A5-6AF568265E92
ms.author: windowsdriverdev
ms.date: 12/9/2017
ms.keywords: SpoolerRefreshPrinterChangeNotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SpoolerRefreshPrinterChangeNotification
req.alt-loc: Winsplp.h
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
req.product: Windows 10 or later.
---

# SpoolerRefreshPrinterChangeNotification function



## -description




## -syntax

````
BOOL WINAPI SpoolerRefreshPrinterChangeNotification(
  _In_        HANDLE                    hPrinter,
  _In_        DWORD                     dwColor,
  _In_        PPRINTER_NOTIFY_OPTIONS   pOptions,
  _Inout_opt_ PPRINTER_NOTIFY_INFO      ppInfo
);
````


## -parameters

### -param hPrinter [in]


### -param dwColor [in]


### -param pOptions [in]


### -param ppInfo [in, out, optional]


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Winsplp.h</dt>
</dl>
</td>
</tr>
</table>