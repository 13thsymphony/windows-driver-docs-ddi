---
UID : NF:sercx.SerCx2SystemDmaReceiveCreate
title : SerCx2SystemDmaReceiveCreate function
author : windows-driver-content
description : The SerCx2SystemDmaReceiveCreate method creates a SerCx2 system-DMA-receive object, which version 2 of the serial framework extension (SerCx2) uses to perform system-DMA-receive transactions.
old-location : serports\sercx2systemdmareceivecreate.htm
old-project : serports
ms.assetid : 62758F49-5CBB-4694-B4F4-12A5372F846F
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : SerCx2SystemDmaReceiveCreate
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : sercx.h
req.include-header : 
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 8.1.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : SerCx2SystemDmaReceiveCreate
req.alt-loc : 2.0\Sercx.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : SERCX_STATUS, *PSERCX_STATUS
req.product : Windows 10 or later.
---


# SerCx2SystemDmaReceiveCreate function
The <b>SerCx2SystemDmaReceiveCreate</b> method creates a SerCx2 system-DMA-receive object, which version 2 of the serial framework extension (SerCx2) uses to perform system-DMA-receive transactions.

## Syntax

````
NTSTATUS SerCx2SystemDmaReceiveCreate(
  [in]           WDFDEVICE                         Device,
  [in]           PSERCX2_SYSTEM_DMA_RECEIVE_CONFIG SystemDmaReceiveConfig,
  [in, optional] PWDF_OBJECT_ATTRIBUTES            Attributes,
  [out]          SERCX2SYSTEMDMARECEIVE            *SystemDmaReceive
);
````

## Parameters

`Device`

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a>.

`SystemDmaReceiveConfig`

A pointer to a <a href="..\sercx\ns-sercx-_sercx2_system_dma_receive_config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a> structure. Before calling this method, the caller must call the <a href="..\sercx\nf-sercx-sercx2_system_dma_receive_config_init.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT</a> or <a href="..\sercx\nf-sercx-sercx2_system_dma_receive_config_init_new_data_notification.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION</a> function to initialize the structure. This structure contains pointers to a set of event callback routines that are implemented by the serial controller driver. SerCx2 calls these functions to perform system-DMA-receive transactions.

`Attributes`

A pointer to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that describes the attributes to assign to the new system-DMA-receive object. Before calling this method, the caller must call the <a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a> function to initialize the structure. This parameter is optional and can be specified as WDF_NO_OBJECT_ATTRIBUTES if the serial controller driver does not need to assign attributes to the object. For more information, see Remarks.

`SystemDmaReceive`

A pointer to a location to which this method writes a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a> handle to the newly created system-DMA-receive object. SerCx2 and the serial controller driver use this handle in subsequent calls to refer to this object.


## Return Value

This method returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>A system-DMA-receive object already exists from a previous <b>SerCx2SystemDmaReceiveCreate</b> call; or a custom-receive object already exists from a previous call to the <a href="..\sercx\nf-sercx-sercx2customreceivecreate.md">SerCx2CustomReceiveCreate</a> method; or a custom-transmit object exists from a previous call to the <a href="..\sercx\nf-sercx-sercx2customtransmitcreate.md">SerCx2CustomTransmitCreate</a> method; or <a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a> has not yet been called to create a PIO-receive object.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The <i>Config</i>-&gt;<b>Size</b> value does not equal <b>sizeof</b>(<b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b>).
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>A parameter value is not valid.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Insufficient resources are available to perform the requested operation.

## Remarks

This method is called by the serial controller driver to create a system-DMA-receive object. SerCx2 uses this object to perform system-DMA-receive transactions, which are I/O transactions that use the system DMA controller to read data received by the serial controller.

Typically, a serial controller driver calls <b>SerCx2SystemDmaReceiveCreate</b> from its <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback function. This function receives a list of hardware resources, which can include system DMA channels.

A serial controller driver must successfully call the <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a> and <a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a> methods before calling <b>SerCx2SystemDmaReceiveCreate</b>.

Before calling <b>SerCx2SystemDmaReceiveCreate</b>, the serial controller driver must call the <a href="..\sercx\nf-sercx-sercx2_system_dma_receive_config_init.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT</a> or <a href="..\sercx\nf-sercx-sercx2_system_dma_receive_config_init_new_data_notification.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION</a> function to initialize the <a href="..\sercx\ns-sercx-_sercx2_system_dma_receive_config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a> structure pointed to by <i>SystemDmaReceiveConfig</i>. These functions set the following members of the structure to zero:

If necessary, the serial controller driver can set any of these members to nonzero values after the initialization function returns. However, for convenience, <b>SerCx2SystemDmaReceiveCreate</b> uses the following default values if these members are zero:

If the calling driver sets <b>Exclusive</b> to <b>TRUE</b>, the <b>MinimumTransferUnitOverride</b>, <b>DmaAlignment</b>, and <b>MinimumTransactionLength</b> members must be zero. For more information, see <a href="..\sercx\ns-sercx-_sercx2_system_dma_receive_config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.

If the specified combination of implemented callback functions is not valid, <b>SerCx2SystemDmaReceiveCreate</b> fails and returns STATUS_INVALID_PARAMETER. The driver must implement either both or neither of the <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_enable_new_data_notification.md">EvtSerCx2SystemDmaReceiveEnableNewDataNotification</a> and <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_cancel_new_data_notification.md">EvtSerCx2SystemDmaReceiveCancelNewDataNotification</a>  functions.

As an option, a serial controller driver can use the <i>Attributes</i> parameter to create a context for the system-DMA-receive object, and to supply pointers to <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> and <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> functions that are called to prepare the object for deletion. For more information, see <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>.

If the <i>Attributes</i> parameter points to a <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure, the caller must not overwrite the values that the <a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a> initialization function writes to the <b>ParentObject</b>, <b>ExecutionLevel</b>, and <b>SynchronizationScope</b> members of this structure.

For more information about creating system-DMA-receive objects, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a>. For more information about system-DMA-receive transactions, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265343">SerCx2 System-DMA-Receive Transactions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | sercx.h |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>
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
<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_cancel_new_data_notification.md">EvtSerCx2SystemDmaReceiveCancelNewDataNotification</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_cleanup_transaction.md">EvtSerCx2SystemDmaReceiveCleanupTransaction</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_enable_new_data_notification.md">EvtSerCx2SystemDmaReceiveEnableNewDataNotification</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_initialize_transaction.md">EvtSerCx2SystemDmaReceiveInitializeTransaction</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2pioreceivecreate.md">SerCx2PioReceiveCreate</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a>
</dt>
<dt>
<a href="..\sercx\ns-sercx-_sercx2_system_dma_receive_config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2_system_dma_receive_config_init.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2_system_dma_receive_config_init_new_data_notification.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION</a>
</dt>
<dt>
<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\wdfobject\nf-wdfobject-wdf_object_attributes_init.md">WDF_OBJECT_ATTRIBUTES_INIT</a>
</dt>
<dt>
<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablerwdmgetdmaadapter.md">WdfDmaEnablerWdmGetDmaAdapter</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2SystemDmaReceiveCreate method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>