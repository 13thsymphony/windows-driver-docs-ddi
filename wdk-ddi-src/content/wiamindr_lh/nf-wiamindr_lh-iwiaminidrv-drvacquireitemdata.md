---
UID: NF:wiamindr_lh.IWiaMiniDrv.drvAcquireItemData
title: IWiaMiniDrv::drvAcquireItemData method
author: windows-driver-content
description: The IWiaMiniDrv::drvAcquireItemData method is called by the WIA service to transfer data from the device to an application.
old-location: image\iwiaminidrv_drvacquireitemdata.htm
old-project: image
ms.assetid: ab49643b-ab77-49ea-9a3b-e3a184cd29d0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: image.iwiaminidrv_drvacquireitemdata, wiamindr_lh/IWiaMiniDrv::drvAcquireItemData, drvAcquireItemData method [Imaging Devices], IWiaMiniDrv interface, IWiaMiniDrv, drvAcquireItemData method [Imaging Devices], drvAcquireItemData, MiniDrv_fb4ad9e4-6648-4038-9b72-4e521d4dd5f2.xml, IWiaMiniDrv::drvAcquireItemData, IWiaMiniDrv interface [Imaging Devices], drvAcquireItemData method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later.
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
req.lib: wiamindr_lh.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	wiamindr_lh.h
apiname:
-	IWiaMiniDrv.drvAcquireItemData
product: Windows
targetos: Windows
req.typenames: SCANWINDOW, *PSCANWINDOW
req.product: Windows 10 or later.
---


# drvAcquireItemData method
The <b>IWiaMiniDrv::drvAcquireItemData</b> method is called by the WIA service to transfer data from the device to an application.

## Syntax

````
HRESULT drvAcquireItemData(
  [in]      BYTE                      *pWiasContext,
  [in]      LONG                      lFlags,
  [in, out] PMINIDRV_TRANSFER_CONTEXT pmdtc,
  [out]     LONG                      *plDevErrVal
);
````

## Parameters

`__MIDL__IWiaMiniDrv0009`



`__MIDL__IWiaMiniDrv0010`



`__MIDL__IWiaMiniDrv0011`



`__MIDL__IWiaMiniDrv0012`




## Return Value

On success, the method should return S_OK and clear the device error value pointed to by <b>plDevErrVal</b>. If the transfer was canceled, the method should return S_FALSE. If the method fails, it should return a standard COM error code and fill in a minidriver-specific error code value in the memory pointed to by <b>plDevErrVal</b>. The <b>Remarks</b> section has additional return-value information that applies to ADF scanning.

## Remarks

There are two main types of transfer: memory-based, and file-based. The WIA service indicates which type is to be performed by the setting of <i>pmdtc</i>--&gt;<b>tymed</b>, which will be TYMED_CALLBACK or TYMED_MULTIPAGE_CALLBACK for memory-based transfers, and TYMED_FILE or TYMED_MULTIPAGE_FILE for file transfers. For more information about these constants, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551656">WIA_IPA_TYMED</a>.
<ul>
<li>
For memory-based transfers, a buffer may or may not have already been allocated, as indicated by the value in <i>pmdtc</i>--&gt;<b>bClassDrvAllocBuf</b>. The WIA service can pass up to two buffers to the minidriver, but typically passes only one. The number of buffers is specified by the value in <i>pmdtc</i>--&gt;<b>lNumBuffers</b>. If memory for the buffer is not already allocated, the minidriver should allocate it using any of the usual means, such as <b>CoTaskMemAlloc</b>, (described in the Windows SDK documentation), or <b>new</b>. If the minidriver allocates a buffer, it also has the responsibility of freeing the buffer.

</li>
<li>
For file transfers, the minidriver should first write the data to the buffer passed in the WIA service's call to this method, and then call <a href="..\wiamdef\nf-wiamdef-wiaswritepagebuftofile.md">wiasWritePageBufToFile</a> to write the buffer data to the file involved. The minidriver should not attempt to use the file handle specified in <b>pmdtc</b>--&gt;<b>hFile</b> to write the data to the file.

</li>
</ul>Periodically, the minidriver should call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543946">IWiaMiniDrvCallBack::MiniDrvCallback</a> method in the COM interface point to by <i>pdmtc</i>--&gt;<b>pIWiaMiniDrvCallBack</b> to update the status of the transfer. For memory-based transfers, this function is used to pass the data back to the application. How often this function should be called is left to the minidriver, but it should be called about ten times, or roughly once per second during the transfer, whichever is more often.

Other transfer parameters that the WIA service provides include the following:
<ul>
<li>
<b>pmdtc</b>--&gt;<b>guidFormatID</b> - the data format

</li>
<li>
<b>pmdtc</b>--&gt;<b>lCompression</b> - the type of compression used

</li>
</ul>A potential problem for ADF-equipped scanners is running out of paper during a scan operation. The HRESULT that your implementation of <b>IWiaMiniDrv::drvAcquireItemData</b> returns depends on the current setting of the scanner's WIA_DPS_PAGES property, and whether all pages were properly scanned. Use the following rules to guide you in determining the appropriate HRESULT to return in this method.
<table>
<tr>
<th>Situation</th>
<th>HRESULT Value</th>
</tr>
<tr>
<td>
The WIA_DPS_PAGES property was set to 0, and the scanner emptied its ADF with no errors.

The WIA_DPS_PAGES property was set to N (where N &gt; 0), and the scanner processed N pages with no errors.

</td>
<td>
S_OK

</td>
</tr>
<tr>
<td>
The WIA_DPS_PAGES property was set to N, and the scanner processed at least one page but ran out of paper before processing all N pages.

</td>
<td>
WIA_STATUS_END_OF_MEDIA

</td>
</tr>
<tr>
<td>
The scanner has unexpectedly detected multiple page feed, stopped scanning, and has set the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551386">WIA_DPS_DOCUMENT_HANDLING_STATUS</a> to MULTIPLE_FEED. 

</td>
<td>
WIA_ERROR_MULTI_FEED 

</td>
</tr>
<tr>
<td>
The scanner ran out of paper on the first scan, regardless of the setting of the WIA_DPS_PAGES property.

A paper jam or other error occurred during the scan operation.

</td>
<td>
Other error code

</td>
</tr>
</table>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Me and in Windows XP and later. Available in Windows Me and in Windows XP and later. |
| **Target Platform** | Desktop |
| **Header** | wiamindr_lh.h (include Wiamindr.h) |
| **Library** | wiamindr_lh.h |

## See Also

<a href="..\wiamindr_lh\ns-wiamindr_lh-_minidrv_transfer_context.md">MINIDRV_TRANSFER_CONTEXT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543982">IWiaMiniDrv::drvGetDeviceErrorStr</a>

<a href="..\wiamindr_lh\nn-wiamindr_lh-iwiaminidrv.md">IWiaMiniDrv</a>

<a href="..\wiamdef\nf-wiamdef-wiasgetimageinformation.md">wiasGetImageInformation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IWiaMiniDrv::drvAcquireItemData method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>