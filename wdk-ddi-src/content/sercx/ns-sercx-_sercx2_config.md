---
UID: NS.SERCX._SERCX2_CONFIG
title: _SERCX2_CONFIG
author: windows-driver-content
description: The SERCX2_CONFIG structure contains configuration information for version 2 of the serial framework extension (SerCx2).
old-location: serports\sercx2_config.htm
old-project: serports
ms.assetid: 9F33E535-21C1-446F-93AA-B86157904F68
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: _SERCX2_CONFIG, *PSERCX2_CONFIG, SERCX2_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: sercx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SERCX2_CONFIG
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
req.irql: Any IRQL
req.product: Windows 10 or later.
---

# _SERCX2_CONFIG structure



## -description
The <b>SERCX2_CONFIG</b> structure contains configuration information for version 2 of the serial framework extension (SerCx2).


## -syntax

````
typedef struct _SERCX2_CONFIG {
  ULONG                                            Size;
  PFN_SERCX2_FILEOPEN                              EvtSerCx2FileOpen;
  PFN_SERCX2_FILECLOSE                             EvtSerCx2FileClose;
  PFN_SERCX2_SET_WAIT_MASK                         EvtSerCx2SetWaitMask;
  PFN_SERCX2_PURGE_FIFOS                           EvtSerCx2PurgeFifos;
  PFN_SERCX2_CONTROL                               EvtSerCx2Control;
  PFN_SERCX2_APPLY_CONFIG                          EvtSerCx2ApplyConfig;
  PFN_SERCX2_SELECT_NEXT_RECEIVE_TRANSACTION_TYPE  EvtSerCx2SelectNextReceiveTransactionType;
  PFN_SERCX2_SELECT_NEXT_TRANSMIT_TRANSACTION_TYPE EvtSerCx2SelectNextTransmitTransactionType;
  PWDF_OBJECT_ATTRIBUTES                           RequestAttributes;
} SERCX2_CONFIG, *PSERCX2_CONFIG;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure. The <a href="serports.sercx2initializedevice">SerCx2InitializeDevice</a> method uses this member to determine which version of the structure the caller is using. The size of this structure might change in future versions of the Sercx.h header file.

### -field EvtSerCx2FileOpen

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_fileopen.md">EvtSerCx2FileOpen</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function. However, a driver that implements this function must also implement an <i>EvtSerCx2FileClose</i> function.

### -field EvtSerCx2FileClose

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_fileclose.md">EvtSerCx2FileClose</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.

### -field EvtSerCx2SetWaitMask

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_set_wait_mask.md">EvtSerCx2SetWaitmask</a> event callback function. This member must point to a valid function.

### -field EvtSerCx2PurgeFifos

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_purge_fifos.md">EvtSerCx2PurgeFifos</a> event callback function. This member must point to a valid function.

### -field EvtSerCx2Control

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_control.md">EvtSerCx2Control</a> event callback function. This member must point to a valid function.

### -field EvtSerCx2ApplyConfig

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_apply_config.md">EvtSerCx2ApplyConfig</a> event callback function. This member must point to a valid function.

### -field EvtSerCx2SelectNextReceiveTransactionType

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_select_next_receive_transaction_type.md">EvtSerCx2SelectNextReceiveTransactionType</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.

### -field EvtSerCx2SelectNextTransmitTransactionType

A pointer to the driver-implemented <a href="..\sercx\nc-sercx-evt_sercx2_select_next_transmit_transaction_type.md">EvtSerCx2SelectNextTransmitTransactionType</a> event callback function. This member is optional and can be set to <b>NULL</b> to indicate that the driver does not implement the function.

### -field RequestAttributes

A pointer to a <a href="kmdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that describes the attributes to assign to the framework request objects that SerCx2 passes to the serial controller driver. Before calling the <a href="serports.sercx2initializedevice">SerCx2InitializeDevice</a> method, the caller must call the <a href="kmdf.wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> function to initialize the structure. This member is optional and can be specified as WDF_NO_OBJECT_ATTRIBUTES if the serial controller driver does not need to assign attributes to the object. For more information, see Remarks.

## -remarks
The <a href="serports.sercx2initializedevice">SerCx2InitializeDevice</a> method accepts a pointer to a <b>SERCX2_CONFIG</b> structure as an input parameter. Before calling <b>SerCx2InitializeDevice</b>, call the <a href="serports.sercx2_config_init">SERCX2_CONFIG_INIT</a> function to initialize this structure.

If the <b>RequestAttributes</b> member points to a <b>WDF_OBJECT_ATTRIBUTES</b> structure, the caller must not overwrite the values that the <a href="kmdf.wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a> initialization function writes to the <b>ParentObject</b>, <b>ExecutionLevel</b>, and <b>SynchronizationScope</b> members of this structure.

A driver might need to store information in context areas in the framework request objects that the driver receives. Typically, the driver calls the <a href="kmdf.wdfdeviceinitsetrequestattributes">WdfDeviceInitSetRequestAttributes</a> method to specify the required attributes for request objects. These attributes include the name and size of the context area in each request object. Additionally, in the current implementation of SerCx2, a serial controller driver that requires a request context should specify these same attributes in the <b>RequestAttributes</b> member of the <b>SERCX2_CONFIG</b> structure that the driver passes to <b>SerCx2InitializeDevice</b>. That is, the driver should specify the same request attributes twice—in the <b>SerCx2InitializeDevice</b> call, and in the <b>WdfDeviceInitSetRequestAttributes</b> call. For more information, see <a href="https://msdn.microsoft.com/29849A8C-6656-444C-BE91-405A4BA2D5B0">SerCx2 Custom-Receive Transactions</a> and <a href="https://msdn.microsoft.com/E72E68BC-A60A-41BE-8606-92A608648042">SerCx2 Custom-Transmit Transactions</a>.

A driver that never needs a request context does not need to call <b>WdfDeviceInitSetRequestAttributes</b>, and can set the <b>RequestAttributes</b> member of the <b>SERCX2_CONFIG</b> structure to WDF_NO_OBJECT_ATTRIBUTES.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported starting with Windows 8.1.
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
</table>

## -see-also
<dl>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_apply_config.md">EvtSerCx2ApplyConfig</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_control.md">EvtSerCx2Control</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_fileclose.md">EvtSerCx2FileClose</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_fileopen.md">EvtSerCx2FileOpen</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_purge_fifos.md">EvtSerCx2PurgeFifos</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_select_next_receive_transaction_type.md">EvtSerCx2SelectNextReceiveTransactionType</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_select_next_transmit_transaction_type.md">EvtSerCx2SelectNextTransmitTransactionType</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_set_wait_mask.md">EvtSerCx2SetWaitmask</a>
</dt>
<dt>
<a href="serports.sercx2_config_init">SERCX2_CONFIG_INIT</a>
</dt>
<dt>
<a href="serports.sercx2initializedevice">SerCx2InitializeDevice</a>
</dt>
<dt>
<a href="kmdf.wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="kmdf.wdf_object_attributes_init">WDF_OBJECT_ATTRIBUTES_INIT</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX2_CONFIG structure%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
