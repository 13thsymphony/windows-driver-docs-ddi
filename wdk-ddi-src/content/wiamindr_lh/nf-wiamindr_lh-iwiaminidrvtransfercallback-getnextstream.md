---
UID : NF:wiamindr_lh.IWiaMiniDrvTransferCallback.GetNextStream
title : IWiaMiniDrvTransferCallback::GetNextStream method
author : windows-driver-content
description : Called by the WIA mini-driver to obtain a stream for the current data transfer (download or upload).
old-location : image\iwiaminidrvtransfercallback_getnextstream.htm
old-project : image
ms.assetid : FF33471A-692B-4568-BF37-1870DEC367D0
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : GetNextStream method [Imaging Devices], IWiaMiniDrvTransferCallback interface, IWiaMiniDrvTransferCallback interface [Imaging Devices], GetNextStream method, GetNextStream method [Imaging Devices], IWiaMiniDrvTransferCallback, GetNextStream, image.iwiaminidrvtransfercallback_getnextstream, wiamindr_lh/IWiaMiniDrvTransferCallback::GetNextStream, IWiaMiniDrvTransferCallback::GetNextStream
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wiamindr_lh.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Windows 8
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
req.lib : wiamindr_lh.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSCANWINDOW, SCANWINDOW"
req.product : Windows 10 or later.
---


# GetNextStream method
Called by the WIA mini-driver to obtain a stream for the current data transfer (download or upload).

## Syntax

````
HRESULT GetNextStream(
  [in]  LONG    lFlags,
  [in]  BSTR    bstrItemName,
  [in]  BSTR    bstrFullItemName,
  [out] IStream **ppIStream
);
````

## Parameters

`lFlags`

Represents flag bits. This parameter is unused and should always be set to zero (0) by the caller.

`bstrItemName`

The name of the item that will perform the data transfer. For more information, see  <a href="https://msdn.microsoft.com/library/windows/hardware/ff551590">WIA_IPA_ITEM_NAME</a>.

`bstrFullItemName`

The full name of the item that will perform the data transfer. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551561">WIA_IPA_FULL_ITEM_NAME</a>.

`ppIStream`

A pointer to an <b>IStream</b> object.


## Return Value

This method returns S_OK when the call is successful. Otherwise it returns an appropriate HRESULT error code.

## Remarks

When the client requests to skip the data transfer, the <b>GetNextStream</b> method returns WIA_STATUS_SKIP_ITEM. The WIA mini-driver must skip the current image transfer and continue with the next image transfer, if any. For example, for a download transfer, finish scanning the current image and then discard the image data.

When the current transfer sequence is cancelled, the <b>GetNextStream</b> method returns S_FALSE.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wiamindr_lh.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551561">WIA_IPA_FULL_ITEM_NAME</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551590">WIA_IPA_ITEM_NAME</a>

<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiaminidrvtransfercallback.md">IWiaMiniDrvTransferCallback</a>

<a href="https://msdn.microsoft.com/83817277-3526-4f64-8e7c-7e02c8cd77bd">Data Transfer Between Legacy Application and Windows Vista Driver</a>

<a href="https://msdn.microsoft.com/0cdc02bf-23fe-4122-8d5f-f42c3c07da8b">Cancellation of Data Transfers in Windows Vista</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaMiniDrvTransferCallback::GetNextStream method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>