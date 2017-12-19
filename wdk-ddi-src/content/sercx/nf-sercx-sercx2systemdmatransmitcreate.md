---
UID: NF.sercx.SerCx2SystemDmaTransmitCreate
title: SerCx2SystemDmaTransmitCreate function
author: windows-driver-content
description: The SerCx2SystemDmaTransmitCreate method creates a SerCx2 system-DMA-transmit object, which version 2 of the serial framework extension (SerCx2) uses to perform system-DMA-transmit transactions.
old-location: serports\sercx2systemdmatransmitcreate.htm
old-project: serports
ms.assetid: CD0FA4A2-9E09-4F76-A332-858CC5D61651
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SerCx2SystemDmaTransmitCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SerCx2SystemDmaTransmitCreate
req.alt-loc: 2.0\Sercx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# SerCx2SystemDmaTransmitCreate function



## -description
The <b>SerCx2SystemDmaTransmitCreate</b> method creates a SerCx2 system-DMA-transmit object, which version 2 of the serial framework extension (SerCx2) uses to perform system-DMA-transmit transactions.



## -syntax

````
NTSTATUS SerCx2SystemDmaTransmitCreate(
  [in]           WDFDEVICE                          Device,
  [in]           PSERCX2_SYSTEM_DMA_TRANSMIT_CONFIG SystemDmaTransmitConfig,
  [in, optional] PWDF_OBJECT_ATTRIBUTES             Attributes,
  [out]          SERCX2SYSTEMDMATRANSMIT            *SystemDmaTransmit
);
````


## -parameters

### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="serports.sercx2initializedevice">SerCx2InitializeDevice</a>.


### -param SystemDmaTransmitConfig [in]

A pointer to a <a href="serports.sercx2_system_dma_transmit_config">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a> structure. Before calling this method, the caller must call the <a href="serports.sercx2_system_dma_transmit_config_init">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT</a> function to initialize the structure. This structure contains pointers to a set of event callback routines that are implemented by the serial controller driver. SerCx2 calls these functions to perform system-DMA-transmit transactions.


### -param Attributes [in, optional]

A pointer to a <a href="kmdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that describes the attributes to assign to the new system-DMA-transmit object. Before calling this method, the caller must call the <a href="kmdf.wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> function to initialize the structure. This parameter is optional and can be specified as WDF_NO_OBJECT_ATTRIBUTES if the serial controller driver does not need to assign attributes to the object. For more information, see Remarks.


### -param SystemDmaTransmit [out]

A pointer to a location to which this method writes a <a href="serports.sercx2systemdmatransmit_object_handle">SERCX2SYSTEMDMATRANSMIT</a> handle to the newly created system-DMA-transmit object. SerCx2 and the serial controller driver use this handle in subsequent calls to refer to this object.


## -returns
This method returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>A system-DMA-transmit object already exists from a previous <b>SerCx2SystemDmaTransmitCreate</b> call; or a custom-transmit object exists from a previous call to the <a href="serports.sercx2customtransmitcreate">SerCx2CustomTransmitCreate</a> method; or a custom-receive object exists from a previous call to the <a href="serports.sercx2customreceivecreate">SerCx2CustomReceiveCreate</a> method; or <a href="serports.sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> has not yet been called to create a PIO-transmit object.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The <i>Config</i>-&gt;<b>Size</b> value does not equal <b>sizeof</b>(<b>SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</b>).
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>A parameter value is not valid.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Insufficient resources are available to create the system-DMA-transmit object.

 


## -remarks
Your serial controller driver can this method to create a system-DMA-transmit object. SerCx2 uses this object to perform system-DMA-transmit transactions, which are transactions that use the system DMA controller to write data to the serial controller to be transmitted.

Typically, a serial controller driver calls <b>SerCx2SystemDmaTransmitCreate</b> from its <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback function. This function receives a list of hardware resources, which can include system DMA channels.

The serial controller driver must successfully call the <a href="serports.sercx2initializedevice">SerCx2InitializeDevice</a> and <a href="serports.sercx2piotransmitcreate">SerCx2PioTransmitCreate</a> methods before calling <b>SerCx2SystemDmaTransmitCreate</b>.

Before calling <b>SerCx2SystemDmaTransmitCreate</b>, the serial controller driver must call the <a href="serports.sercx2_system_dma_transmit_config_init">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT</a> function to initialize the <a href="serports.sercx2_system_dma_transmit_config">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a> structure pointed to by <i>SystemDmaTransmitConfig</i>. This function sets the following members of the structure to zero:

If necessary, the serial controller driver can set any of these members to nonzero values after the initialization function returns. However, for convenience, <b>SerCx2SystemDmaTransmitCreate</b> uses the following default values if these members are zero:

If the calling driver sets <b>Exclusive</b> to <b>TRUE</b>, the <b>MinimumTransferUnitOverride</b>, <b>DmaAlignment</b>, and <b>MinimumTransactionLength</b> members must be zero. For more information, see <a href="serports.sercx2_system_dma_transmit_config">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a>.

If the specified combination of implemented callback functions is not valid, <b>SerCx2SystemDmaTransmitCreate</b> fails and returns STATUS_INVALID_PARAMETER. The driver must implement either all three or none of the <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_drain_fifo.md">EvtSerCx2SystemDmaTransmitDrainFifo</a>,  <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_cancel_drain_fifo.md">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a>, and <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo.md">EvtSerCx2SystemDmaTransmitPurgeFifo</a> functions.

As an option, a serial controller driver can use the <i>Attributes</i> parameter to create a context for the system-DMA-transmit object, and to supply pointers to <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> and <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> functions that are called to prepare the object for deletion. For more information, see <a href="kmdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>.

If the <i>Attributes</i> parameter points to a <a href="kmdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure, the caller must not overwrite the values that the <a href="kmdf.wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> initialization function writes to the <b>ParentObject</b>, <b>ExecutionLevel</b>, and <b>SynchronizationScope</b> members of this structure.

For more information about creating system-DMA-transmit objects, see <a href="serports.sercx2systemdmatransmit_object_handle">SERCX2SYSTEMDMATRANSMIT</a>. For more information about system-DMA-transmit transactions, see <a href="https://msdn.microsoft.com/8569E76F-CAFF-4A2C-8052-62B340C5ADED">SerCx2 System-DMA-Transmit Transactions</a>.


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
Version

</th>
<td width="70%">
Available starting with Windows 8.1.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>2.0\Sercx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.dma_adapter">DMA_ADAPTER</a>
</dt>
<dt>
<a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a>
</dt>
<dt>
<a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a>
</dt>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a>
</dt>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_cancel_drain_fifo.md">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_cleanup_transaction.md">EvtSerCx2SystemDmaTransmitCleanupTransaction</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_drain_fifo.md">EvtSerCx2SystemDmaTransmitDrainFifo</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_initialize_transaction.md">EvtSerCx2SystemDmaTransmitInitializeTransaction</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo.md">EvtSerCx2SystemDmaTransmitPurgeFifo</a>
</dt>
<dt>
<a href="serports.sercx2initializedevice">SerCx2InitializeDevice</a>
</dt>
<dt>
<a href="serports.sercx2piotransmitcreate">SerCx2PioTransmitCreate</a>
</dt>
<dt>
<a href="serports.sercx2systemdmatransmit_object_handle">SERCX2SYSTEMDMATRANSMIT</a>
</dt>
<dt>
<a href="serports.sercx2_system_dma_transmit_config">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a>
</dt>
<dt>
<a href="serports.sercx2_system_dma_transmit_config_init">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG_INIT</a>
</dt>
<dt>
<a href="kmdf.wdfdmaenablerwdmgetdmaadapter">WdfDmaEnablerWdmGetDmaAdapter</a>
</dt>
<dt>
<a href="kmdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="kmdf.wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2SystemDmaTransmitCreate method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

