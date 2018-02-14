---
UID: NF:wia_lh.IWiaLog.hResult
title: IWiaLog::hResult method
author: windows-driver-content
description: Note that the IWiaLog interface is obsolete for Microsoft Windows XP and later, and is no longer supported.
old-location: image\iwialog_hresult.htm
old-project: image
ms.assetid: 74d9b770-c2b6-483d-a6d7-070ac2a55133
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: hResult method [Imaging Devices], IWiaLog interface, hResult, IWiaLog interface [Imaging Devices], hResult method, IWiaLog::hResult, wia_lh/IWiaLog::hResult, hResult method [Imaging Devices], IWiaLog, image.iwialog_hresult, IWiaLog_e581a82d-60c1-45e3-9d5a-fcac2b4d9c9c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wia_lh.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me, Windows XP, and later. Obsoletefor Microsoft Windows XP and later, and is no longer supported. Instead, use the Diagnostic Log Macros.
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
req.lib: wia_lh.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	wia_lh.h
apiname:
-	IWiaLog.hResult
product: Windows
targetos: Windows
req.typenames: BMP_IMAGE_INFO, *PBMP_IMAGE_INFO
req.product: Windows 10 or later.
---


# hResult method
Note that the <b>IWiaLog</b> interface is <b>obsolete </b>for Microsoft Windows XP and later, and is no longer supported. Instead, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540599">Diagnostic Log Macros</a>.

The <b>IWiaLog::hResult</b> method translates an HRESULT value into a string and writes the string to <i>Wiaservc.log</i>.

## Syntax

````
HRESULT hResult(
  [in] HRESULT hResult
);
````

## Parameters

`hResult`

Specifies the HRESULT value to translate into a string.


## Return Value

If the method succeeds, it returns S_OK. If the method fails, it returns a standard COM error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me, Windows XP, and later. Obsoletefor Microsoft Windows XP and later, and is no longer supported. Instead, use the Diagnostic Log Macros. Available in Windows Me, Windows XP, and later. Obsoletefor Microsoft Windows XP and later, and is no longer supported. Instead, use the Diagnostic Log Macros. |
| **Target Platform** | Desktop |
| **Header** | wia_lh.h |
| **Library** | wia_lh.h |