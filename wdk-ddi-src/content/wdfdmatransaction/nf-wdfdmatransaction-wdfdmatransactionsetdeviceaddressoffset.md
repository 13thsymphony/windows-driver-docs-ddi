---
UID: NF.wdfdmatransaction.WdfDmaTransactionSetDeviceAddressOffset
title: WdfDmaTransactionSetDeviceAddressOffset function
author: windows-driver-content
description: The WdfDmaTransactionSetDeviceAddressOffset method specifies the offset of the register that the system DMA controller will access when performing the DMA operation.
old-location: wdf\wdfdmatransactionsetdeviceaddressoffset.htm
old-project: wdf
ms.assetid: A45231E0-0807-41AA-B20F-6335067BE99A
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfDmaTransactionSetDeviceAddressOffset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.alt-api: WdfDmaTransactionSetDeviceAddressOffset
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfDmaTransactionSetDeviceAddressOffset function



## -description
<p class="CCE_Message">[Applies to KMDF only]

   The 
  <b>WdfDmaTransactionSetDeviceAddressOffset</b> method specifies the offset of the register that the system DMA controller will access when performing the DMA operation.


## -syntax

````
void WdfDmaTransactionSetDeviceAddressOffset(
  _In_ WDFDMATRANSACTION DmaTransaction,
  _In_ ULONG             Offset
);
````


## -parameters

### -param DmaTransaction [in]

A handle to a DMA transaction object that specifies the transaction to modify.

### -param Offset [in]

The offset of the register, from the <b>DeviceAddress</b> specified in <a href="wdf.wdf_dma_system_profile_config">WDF_DMA_SYSTEM_PROFILE_CONFIG</a>, to or from which DMA should be performed.

## -returns
This method does not return a value.

## -remarks
<b>WdfDmaTransactionSetDeviceAddressOffset</b> must be used with a DMA enabler that specifies a system-mode DMA profile.

Framework-based drivers call <b>WdfDmaTransactionSetDeviceAddressOffset</b> after initializing a DMA transaction and before executing it.

A driver can use this method to access multiple registers within a device's register file.

For example, a driver might use DMA to access separate read and write registers in a device's register file.

To do so, the driver specifies the base address of the device's register file when configuring the enabler, and then sets the offset of the read or write register as necessary before executing the transaction.

If your driver calls this method on an operating system earlier than Windows 8, <a href="wdf.using_kmdf_verifier">the framework's verifier</a> reports an error.

The following code example initializes a DMA transaction.  It then sets the offset of the register that the system DMA controller will access, provides a transfer completion callback routine, and executes the DMA transaction.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum support
</th>
<td width="70%">
Windows 8
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.11
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfdmatransaction.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;=DISPATCH_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_dma_system_profile_config">WDF_DMA_SYSTEM_PROFILE_CONFIG</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionSetDeviceAddressOffset method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
