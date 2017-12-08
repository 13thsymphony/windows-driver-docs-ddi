---
UID: NI.ntddchgr.IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS
title: IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS
author: windows-driver-content
description: Initializes the status of all elements or of specified number of elements of a particular type.
old-location: storage\ioctl_changer_initialize_element_status.htm
old-project: storage
ms.assetid: 25cbb42a-7263-47b7-84c7-cfcb41a858c8
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _ELEMENT_TYPE, *PELEMENT_TYPE, ELEMENT_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddchgr.h
req.include-header: Ntddchgr.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS
req.alt-loc: Ntddchgr.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS IOCTL



## -description

Initializes the status of all elements or of specified number of elements of a particular type. 

Initializes the status of all elements or of specified number of elements of a particular type. 


## -ioctlparameters

### -input-buffer
<a id="Input_Buffer"></a><a id="input_buffer"></a><a id="INPUT_BUFFER"></a>Input Buffer
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(CHANGER_INITIALIZE_ELEMENT_STATUS). The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains an <a href="storage.changer_initialize_element_status">CHANGER_INITIALIZE_ELEMENT_STATUS</a> structure that indicates the element type and the number of elements to initialize. If the <b>BarCodeScan</b> member is <b>TRUE</b> and CHANGER_BAR_CODE_SCANNER_INSTALLED is also set in <b>Features0</b> of <a href="storage.get_changer_buffer">GET_CHANGER_BUFFER</a>, the elements should be initialized using a bar code scan. 
<b>Parameters.DeviceIoControl.InputBufferLength</b>Parameters.DeviceIoControl.InputBufferLength in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= <b>sizeof</b>sizeof(CHANGER_INITIALIZE_ELEMENT_STATUS). The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>Irp->AssociatedIrp.SystemBuffer contains an <a href="storage.changer_initialize_element_status">CHANGER_INITIALIZE_ELEMENT_STATUS</a><b>CHANGER_INITIALIZE_ELEMENT_STATUS</b>CHANGER_INITIALIZE_ELEMENT_STATUS structure that indicates the element type and the number of elements to initialize. If the <b>BarCodeScan</b>BarCodeScan member is <b>TRUE</b>TRUE and CHANGER_BAR_CODE_SCANNER_INSTALLED is also set in <b>Features0</b>Features0 of <a href="storage.get_changer_buffer">GET_CHANGER_BUFFER</a><b>GET_CHANGER_BUFFER</b>GET_CHANGER_BUFFER, the elements should be initialized using a bar code scan. 


### -input-buffer-length

<text></text>

### -output-buffer
<a id="Output_Buffer"></a><a id="output_buffer"></a><a id="OUTPUT_BUFFER"></a>Output Buffer
NoneNone


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
<a id="I_O_Status_Block"></a><a id="i_o_status_block"></a><a id="I_O_STATUS_BLOCK"></a>I/O Status Block
The <b>Information</b> field is set to <b>sizeof</b>(CHANGER_INITIALIZE_ELEMENT_STATUS). The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_ELEMENT_ADDRESS, or STATUS_INVALID_PARAMETER. The <b>Information</b>Information field is set to <b>sizeof</b>sizeof(CHANGER_INITIALIZE_ELEMENT_STATUS). The <b>Status</b>Status field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_ELEMENT_ADDRESS, or STATUS_INVALID_PARAMETER. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddchgr.h (include Ntddchgr.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.changer_initialize_element_status">CHANGER_INITIALIZE_ELEMENT_STATUS</a>
</dt>
<dt>
<a href="storage.changerinitializeelementstatus">ChangerInitializeElementStatus</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS control code%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
