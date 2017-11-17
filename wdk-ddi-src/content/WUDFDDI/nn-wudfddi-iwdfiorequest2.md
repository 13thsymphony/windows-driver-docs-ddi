---
UID: NN.wudfddi.IWDFIoRequest2
title: IWDFIoRequest2
author: windows-driver-content
description: To obtain the IWDFIoRequest2 interface, drivers call IWDFIoRequest::QueryInterface.
old-location: wdf\iwdfiorequest2.htm
ms.assetid: 6a6285c9-8366-4487-a1c5-38aa24d172a9
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: interface
ms.prod: windows-hardware
ms.technology: wdf
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: IWDFIoRequest2
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: <= DISPATCH_LEVEL
ms.keywords: IWDFWorkItem, GetParentObject, IWDFWorkItem::GetParentObject
req.iface: IWDFWorkItem
req.product: Windows 10 or later.
---

# IWDFIoRequest2 interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>To obtain the <b>IWDFIoRequest2</b> interface, drivers call <b>IWDFIoRequest::QueryInterface</b>.</p>


## -inheritance
<p>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFIoRequest2</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>. <b>IWDFIoRequest2</b> also has these types of members:</p>

<p>The <b>IWDFIoRequest2</b> interface has these methods.</p>

<p>The <a href="https://msdn.microsoft.com/bc34d86b-fa0e-419e-9342-61df12a8e484">GetCreateParametersEx</a> method retrieves file creation parameters that are associated with a file that is being created or opened.</p>

<p>The <a href="https://msdn.microsoft.com/76909efd-99ca-4e47-9c81-8a48608c2543">GetEffectiveIoType</a> method returns the buffer access method that UMDF is using for the data buffers of the I/O request that the <b>IWDFIoRequest2</b> interface represents.</p>

<p>The <a href="https://msdn.microsoft.com/e189d2f6-ef1c-45ed-8b55-8aae0661a426">GetQueryInformationParameters</a> method retrieves parameters that are associated with a <a href="https://msdn.microsoft.com/a883f22e-0d6f-4755-882b-ad5a60a09271">WdfRequestQueryInformation</a>-typed I/O request.</p>

<p>The <a href="https://msdn.microsoft.com/8f918bc4-d2d0-4d5b-93c8-89f02c81a701">GetRequestorMode</a> method indicates whether an I/O request came from a kernel-mode driver or a user-mode component (either an application or a user-mode driver).</p>

<p>The <a href="https://msdn.microsoft.com/44872d92-4a71-4cc7-9f7c-c95477ac3264">GetSetInformationParameters</a> method retrieves parameters that are associated with a <a href="https://msdn.microsoft.com/library/windows/hardware/ff550032">WdfRequestSetInformation</a>-typed I/O request.</p>

<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/hh406321">GetStatus</a> method returns the status of an I/O request.</p>

<p>The <a href="https://msdn.microsoft.com/68523fcb-bb0d-492f-b6ae-3dab4f6aa637">IsCanceled</a> method determines whether the I/O manager has attempted to cancel an I/O request.</p>

<p>The <a href="https://msdn.microsoft.com/17a1e4d8-5438-42b6-b4a5-335e7bd57b1b">IsFromUserModeDriver</a> method indicates whether an I/O request came from a user-mode driver or an application.</p>

<p>The <a href="https://msdn.microsoft.com/1e33f284-6cb9-426f-a900-76b827341927">Requeue</a> method returns an I/O request to the head of the I/O queue from which it was delivered to the driver.</p>

<p>The <a href="https://msdn.microsoft.com/fa02a787-502c-48a3-a5e1-710d7513c42e">RequestRetrieveInputBuffer</a> method retrieves an I/O request's input buffer.</p>

<p>The <a href="https://msdn.microsoft.com/32596330-6cd9-4f82-9140-7f9a26cf7932">RetrieveInputMemory</a> method retrieves the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface of a framework memory object that represents an I/O request's input buffer.</p>

<p>The <a href="https://msdn.microsoft.com/5f12dd97-d8e7-4fef-91bf-00243c0cdd52">RequestRetrieveOutputBuffer</a> method retrieves an I/O request's output buffer.</p>

<p>The <a href="https://msdn.microsoft.com/d17e7435-adc3-4248-a6c9-c7e267504291">RetrieveOutputMemory</a> method retrieves the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface of a framework memory object that represents an I/O request's output buffer.</p>

<p>The <a href="https://msdn.microsoft.com/21d04633-3b68-4c89-a0b9-81507a1bb6d3">Reuse</a> method reinitializes a framework request object so that it can be reused.</p>

<p>The <a href="https://msdn.microsoft.com/af4ae2c0-b1e1-45af-bd0e-3b9a91566caa">StopAcknowledge</a> method informs the framework that the driver has stopped processing a specified I/O request.</p>

<p> </p>

## -members
<p>The <b>IWDFIoRequest2</b> interface has these methods.</p><table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558989">IWDFIoRequest2::GetCreateParametersEx</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/bc34d86b-fa0e-419e-9342-61df12a8e484">GetCreateParametersEx</a> method retrieves file creation parameters that are associated with a file that is being created or opened.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558994">IWDFIoRequest2::GetEffectiveIoType</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/76909efd-99ca-4e47-9c81-8a48608c2543">GetEffectiveIoType</a> method returns the buffer access method that UMDF is using for the data buffers of the I/O request that the <b>IWDFIoRequest2</b> interface represents.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558997">IWDFIoRequest2::GetQueryInformationParameters</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/e189d2f6-ef1c-45ed-8b55-8aae0661a426">GetQueryInformationParameters</a> method retrieves parameters that are associated with a <a href="https://msdn.microsoft.com/a883f22e-0d6f-4755-882b-ad5a60a09271">WdfRequestQueryInformation</a>-typed I/O request.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559002">IWDFIoRequest2::GetRequestorMode</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/8f918bc4-d2d0-4d5b-93c8-89f02c81a701">GetRequestorMode</a> method indicates whether an I/O request came from a kernel-mode driver or a user-mode component (either an application or a user-mode driver).</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559009">IWDFIoRequest2::GetSetInformationParameters</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/44872d92-4a71-4cc7-9f7c-c95477ac3264">GetSetInformationParameters</a> method retrieves parameters that are associated with a <a href="https://msdn.microsoft.com/library/windows/hardware/ff550032">WdfRequestSetInformation</a>-typed I/O request.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559013">IWDFIoRequest2::GetStatus</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/hh406321">GetStatus</a> method returns the status of an I/O request.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559018">IWDFIoRequest2::IsCanceled</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/68523fcb-bb0d-492f-b6ae-3dab4f6aa637">IsCanceled</a> method determines whether the I/O manager has attempted to cancel an I/O request.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559021">IWDFIoRequest2::IsFromUserModeDriver</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/17a1e4d8-5438-42b6-b4a5-335e7bd57b1b">IsFromUserModeDriver</a> method indicates whether an I/O request came from a user-mode driver or an application.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559028">IWDFIoRequest2::Requeue</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/1e33f284-6cb9-426f-a900-76b827341927">Requeue</a> method returns an I/O request to the head of the I/O queue from which it was delivered to the driver.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559033">IWDFIoRequest2::RetrieveInputBuffer</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/fa02a787-502c-48a3-a5e1-710d7513c42e">RequestRetrieveInputBuffer</a> method retrieves an I/O request's input buffer.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559037">IWDFIoRequest2::RetrieveInputMemory</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/32596330-6cd9-4f82-9140-7f9a26cf7932">RetrieveInputMemory</a> method retrieves the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface of a framework memory object that represents an I/O request's input buffer.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559041">IWDFIoRequest2::RetrieveOutputBuffer</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/5f12dd97-d8e7-4fef-91bf-00243c0cdd52">RequestRetrieveOutputBuffer</a> method retrieves an I/O request's output buffer.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559046">IWDFIoRequest2::RetrieveOutputMemory</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/d17e7435-adc3-4248-a6c9-c7e267504291">RetrieveOutputMemory</a> method retrieves the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface of a framework memory object that represents an I/O request's output buffer.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559048">IWDFIoRequest2::Reuse</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/21d04633-3b68-4c89-a0b9-81507a1bb6d3">Reuse</a> method reinitializes a framework request object so that it can be reused.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559051">IWDFIoRequest2::StopAcknowledge</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/af4ae2c0-b1e1-45af-bd0e-3b9a91566caa">StopAcknowledge</a> method informs the framework that the driver has stopped processing a specified I/O request.</p>
</td>
</tr>
</table><p>The <a href="https://msdn.microsoft.com/bc34d86b-fa0e-419e-9342-61df12a8e484">GetCreateParametersEx</a> method retrieves file creation parameters that are associated with a file that is being created or opened.</p>

<p>The <a href="https://msdn.microsoft.com/76909efd-99ca-4e47-9c81-8a48608c2543">GetEffectiveIoType</a> method returns the buffer access method that UMDF is using for the data buffers of the I/O request that the <b>IWDFIoRequest2</b> interface represents.</p>

<p>The <a href="https://msdn.microsoft.com/e189d2f6-ef1c-45ed-8b55-8aae0661a426">GetQueryInformationParameters</a> method retrieves parameters that are associated with a <a href="https://msdn.microsoft.com/a883f22e-0d6f-4755-882b-ad5a60a09271">WdfRequestQueryInformation</a>-typed I/O request.</p>

<p>The <a href="https://msdn.microsoft.com/8f918bc4-d2d0-4d5b-93c8-89f02c81a701">GetRequestorMode</a> method indicates whether an I/O request came from a kernel-mode driver or a user-mode component (either an application or a user-mode driver).</p>

<p>The <a href="https://msdn.microsoft.com/44872d92-4a71-4cc7-9f7c-c95477ac3264">GetSetInformationParameters</a> method retrieves parameters that are associated with a <a href="https://msdn.microsoft.com/library/windows/hardware/ff550032">WdfRequestSetInformation</a>-typed I/O request.</p>

<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/hh406321">GetStatus</a> method returns the status of an I/O request.</p>

<p>The <a href="https://msdn.microsoft.com/68523fcb-bb0d-492f-b6ae-3dab4f6aa637">IsCanceled</a> method determines whether the I/O manager has attempted to cancel an I/O request.</p>

<p>The <a href="https://msdn.microsoft.com/17a1e4d8-5438-42b6-b4a5-335e7bd57b1b">IsFromUserModeDriver</a> method indicates whether an I/O request came from a user-mode driver or an application.</p>

<p>The <a href="https://msdn.microsoft.com/1e33f284-6cb9-426f-a900-76b827341927">Requeue</a> method returns an I/O request to the head of the I/O queue from which it was delivered to the driver.</p>

<p>The <a href="https://msdn.microsoft.com/fa02a787-502c-48a3-a5e1-710d7513c42e">RequestRetrieveInputBuffer</a> method retrieves an I/O request's input buffer.</p>

<p>The <a href="https://msdn.microsoft.com/32596330-6cd9-4f82-9140-7f9a26cf7932">RetrieveInputMemory</a> method retrieves the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface of a framework memory object that represents an I/O request's input buffer.</p>

<p>The <a href="https://msdn.microsoft.com/5f12dd97-d8e7-4fef-91bf-00243c0cdd52">RequestRetrieveOutputBuffer</a> method retrieves an I/O request's output buffer.</p>

<p>The <a href="https://msdn.microsoft.com/d17e7435-adc3-4248-a6c9-c7e267504291">RetrieveOutputMemory</a> method retrieves the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface of a framework memory object that represents an I/O request's output buffer.</p>

<p>The <a href="https://msdn.microsoft.com/21d04633-3b68-4c89-a0b9-81507a1bb6d3">Reuse</a> method reinitializes a framework request object so that it can be reused.</p>

<p>The <a href="https://msdn.microsoft.com/af4ae2c0-b1e1-45af-bd0e-3b9a91566caa">StopAcknowledge</a> method informs the framework that the driver has stopped processing a specified I/O request.</p>

<p> </p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>End of support</p>
</th>
<td width="70%">
<p>Unavailable in UMDF 2.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>1.9</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wudfddi.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>