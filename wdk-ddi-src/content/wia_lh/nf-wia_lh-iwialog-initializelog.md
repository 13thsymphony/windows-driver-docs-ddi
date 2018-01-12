---
UID: NF:wia_lh.IWiaLog.InitializeLog
title: IWiaLog::InitializeLog method
author: windows-driver-content
description: Note that the IWiaLog interface is obsolete for Microsoft Windows XP and later, and is no longer supported. Instead, use the Diagnostic Log Macros.The IWiaLog::InitializeLog method initializes the lWiaLog interface.
old-location: image\iwialog_initializelog.htm
old-project: image
ms.assetid: ef637329-a291-445b-8ac7-6e55d5d7931e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IWiaLog, IWiaLog::InitializeLog, InitializeLog
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wia_lh.h
req.include-header: Wia.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me, Windows XP, and later. Obsoletefor Microsoft Windows XP and later, and is no longer supported. Instead, use the Diagnostic Log Macros.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IWiaLog.InitializeLog
req.alt-loc: wia_lh.h
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
req.typenames: *PBMP_IMAGE_INFO, BMP_IMAGE_INFO
req.product: Windows 10 or later.
---

# IWiaLog::InitializeLog method



## -description
Note that the <b>IWiaLog</b> interface is <b>obsolete</b> for Microsoft Windows XP and later, and is no longer supported. Instead, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540599">Diagnostic Log Macros</a>.

The <b>IWiaLog::InitializeLog</b> method initializes the <b>lWiaLog</b> interface.



## -syntax

````
HRESULT InitializeLog(
  [in] LONG hInstance
);
````


## -parameters

### -param hInstance [in]

Specifies the module handle. This parameter indicates which module is calling the method.


## -returns
If the method succeeds, it returns S_OK. If the method fails, it returns a standard COM error code.


## -remarks
The minidriver should call <b>CoCreateInstance</b> or <b>CoCreateInstanceEx </b>(which are described in the Microsoft Windows SDK documentation) to obtain the <b>IWiaLog</b> interface.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Me, Windows XP, and later. Obsoletefor Microsoft Windows XP and later, and is no longer supported. Instead, use the Diagnostic Log Macros.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wia_lh.h (include Wia.h)</dt>
</dl>
</td>
</tr>
</table>