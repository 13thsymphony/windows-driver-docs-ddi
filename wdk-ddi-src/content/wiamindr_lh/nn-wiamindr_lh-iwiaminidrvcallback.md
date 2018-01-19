---
UID : NN:wiamindr_lh.IWiaMiniDrvCallBack
title : IWiaMiniDrvCallBack
author : windows-driver-content
description : The IWiaMiniDrvCallBack interface provides the MiniDrvCallback method, which enables minidrivers to transfer image header data and image data from the imaging device to the WIA service.
old-location : image\iwiaminidrvcallback_interface.htm
old-project : image
ms.assetid : cf2460c5-325f-43c3-a1fe-5b6982234194
ms.author : windowsdriverdev
ms.date : 1/17/2018
ms.keywords : IWiaMiniDrvTransferCallback, IWiaMiniDrvTransferCallback::SendMessage, SendMessage
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : interface
req.header : wiamindr_lh.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IWiaMiniDrvCallBack
req.alt-loc : wiamindr_lh.h
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
req.typenames : "*PSCANWINDOW, SCANWINDOW"
req.product : Windows 10 or later.
---

# IWiaMiniDrvCallBack interface

The <b>IWiaMiniDrvCallBack</b> interface provides the <a href="https://msdn.microsoft.com/7d1c0d8a-65db-47fd-ad6a-a83c7ed3acd9">MiniDrvCallback</a> method, which enables minidrivers to transfer image header data and image data from the imaging device to the WIA service.

This method can also convey status information, such as the percentage of data transferred.

## Methods

<p>The <b>IWiaMiniDrvCallBack</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [wiamindr_lh.IWiaMiniDrvCallBack.MiniDrvCallback](nf-wiamindr_lh-iwiaminidrvcallback-minidrvcallback.md) | The MiniDrvCallback method provides a callback method for WIA minidrivers to use during a callback data transfer. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum UMDF version** |  |
| **Header** | wiamindr_lh.h |
| **DLL** |  |