---
UID: NF.sercx.SerCx2CustomReceiveTransactionCreate
title: SerCx2CustomReceiveTransactionCreate function
author: windows-driver-content
description: The SerCx2CustomReceiveTransactionCreate method creates a custom-receive-transaction object, which version 2 of the serial framework extension (SerCx2) uses to perform custom-receive transactions.
old-location: serports\sercx2customreceivetransactioncreate.htm
old-project: serports
ms.assetid: 3E01268B-69DB-4713-841B-8B27D24F8431
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: SerCx2CustomReceiveTransactionCreate
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
req.alt-api: SerCx2CustomReceiveTransactionCreate
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

# SerCx2CustomReceiveTransactionCreate function



## -description
The <b>SerCx2CustomReceiveTransactionCreate</b> method creates a custom-receive-transaction object, which version 2 of the serial framework extension (SerCx2) uses to perform custom-receive transactions.



## -syntax

````
NTSTATUS SerCx2CustomReceiveTransactionCreate(
  [in]  SERCX2CUSTOMRECEIVE                       CustomReceive,
  [in]  PSERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG CustomReceiveTransactionConfig,
  [in]  PWDF_OBJECT_ATTRIBUTES                    Attributes,
  [out] SERCX2CUSTOMRECEIVETRANSACTION            *CustomReceiveTransaction
);
````


## -parameters

### -param CustomReceive [in]

A <a href="serports.sercx2customreceive">SERCX2CUSTOMRECEIVE</a> handle to a custom-receive object. The serial controller driver previously called the <a href="serports.sercx2customreceivecreate">SerCx2CustomReceiveCreate</a> method to create this object.


### -param CustomReceiveTransactionConfig [in]

A pointer to a <a href="serports.sercx2_custom_receive_transaction_config">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a> structure. Before calling this method, the caller must call the <a href="serports.sercx2_custom_receive_transaction_config_init">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT</a> function to initialize the structure. This structure contains pointers to a set of event callback routines that are implemented by the serial controller driver. SerCx2 calls these functions to do an I/O transaction that uses the custom data-transfer mechanism to read data received by the serial controller.


### -param Attributes [in]

A pointer to a <a href="kmdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that describes the attributes to assign to the new custom-receive-transaction object. Before calling this method, the caller must call the <a href="kmdf.wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> function to initialize the structure. This parameter is optional and can be specified as WDF_NO_OBJECT_ATTRIBUTES if the serial controller driver does not need to assign attributes to the object. For more information, see Remarks.


### -param CustomReceiveTransaction [out]

A pointer to a location to which this method writes a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a> handle to the newly created custom-receive-transaction object. SerCx2 and the serial controller driver use this handle in subsequent calls to refer to this object.


## -returns
This method returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>A custom-receive-transaction object already exists from a previous <b>SerCx2CustomReceiveTransactionCreate</b> call.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The <i>CustomReceiveTransactionConfig</i>-&gt;<b>Size</b> value does not equal <b>sizeof</b>(<b>SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</b>).
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>A parameter value is not valid. The caller must supply valid <a href="..\sercx\nc-sercx-evt_sercx2_custom_receive_transaction_start.md">EvtSerCx2CustomReceiveTransactionStart</a> and <a href="serports.evtsercx2customreceivetransactionqueryprogress">EvtSerCx2CustomReceiveTransactionQueryProgress</a> function pointers.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>Insufficient resources are available to create the custom-receive-transaction object.

 


## -remarks
Your serial controller driver can call this method to create a custom-receive-transaction object. SerCx2 uses this object to manage custom-receive transactions, which are I/O transactions that use a custom data-transfer mechanism to read data received by the serial controller.

As an option, a serial controller driver can use the <i>Attributes</i> parameter to create a context for the custom-receive object, and to supply pointers to <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> and <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a> functions that are called to prepare the object for deletion. For more information, see <a href="kmdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>.

If the <i>Attributes</i> parameter points to a <a href="kmdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure, the caller must not overwrite the values that the <a href="kmdf.wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> initialization function writes to the <b>ParentObject</b>, <b>ExecutionLevel</b>, and <b>SynchronizationScope</b> members of this structure.

If the specified combination of implemented callback functions is not valid, the <b>SerCx2CustomReceiveTransactionCreate</b> call fails and returns STATUS_INVALID_PARAMETER.

For more information about creating custom-receive-transaction objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a>. For more information about custom-receive transactions, see <a href="https://msdn.microsoft.com/29849A8C-6656-444C-BE91-405A4BA2D5B0">SerCx2 Custom-Receive Transactions</a>.


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
<a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a>
</dt>
<dt>
<a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_destroy.md">EvtDestroyCallback</a>
</dt>
<dt>
<a href="serports.evtsercx2customreceivetransactionqueryprogress">EvtSerCx2CustomReceiveTransactionQueryProgress</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_custom_receive_transaction_start.md">EvtSerCx2CustomReceiveTransactionStart</a>
</dt>
<dt>
<a href="serports.sercx2customreceive">SERCX2CUSTOMRECEIVE</a>
</dt>
<dt>
<a href="serports.sercx2customreceivecreate">SerCx2CustomReceiveCreate</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265249">SERCX2CUSTOMRECEIVETRANSACTION</a>
</dt>
<dt>
<a href="serports.sercx2_custom_receive_transaction_config">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG</a>
</dt>
<dt>
<a href="serports.sercx2_custom_receive_transaction_config_init">SERCX2_CUSTOM_RECEIVE_TRANSACTION_CONFIG_INIT</a>
</dt>
<dt>
<a href="kmdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="kmdf.wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2CustomReceiveTransactionCreate method%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

