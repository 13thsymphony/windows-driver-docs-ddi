---
UID: NS.ntddchgr._CHANGER_INITIALIZE_ELEMENT_STATUS
title: CHANGER_INITIALIZE_ELEMENT_STATUS
author: windows-driver-content
description: The CHANGER_INITIALIZE_ELEMENT_STATUS structure is used in conjunction with the IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS request to initialize the status of all elements or of a specified number of elements of a particular type.
old-location: storage\changer_initialize_element_status.htm
old-project: storage
ms.assetid: fd26a97d-cbea-4ab4-b54e-1831d6e3a8ed
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: CHANGER_INITIALIZE_ELEMENT_STATUS, CHANGER_INITIALIZE_ELEMENT_STATUS, *PCHANGER_INITIALIZE_ELEMENT_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddchgr.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CHANGER_INITIALIZE_ELEMENT_STATUS
req.alt-loc: ntddchgr.h
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
req.iface: 
---

# CHANGER_INITIALIZE_ELEMENT_STATUS structure



## -description
<p>The CHANGER_INITIALIZE_ELEMENT_STATUS structure is used in conjunction with the <a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-initialize-element-status.md">IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS</a> request to initialize the status of all elements or of a specified number of elements of a particular type. </p>


## -syntax

````
typedef struct _CHANGER_INITIALIZE_ELEMENT_STATUS {
  CHANGER_ELEMENT_LIST ElementList;
  BOOLEAN              BarCodeScan;
} CHANGER_INITIALIZE_ELEMENT_STATUS, *PCHANGER_INITIALIZE_ELEMENT_STATUS;
````


## -struct-fields
<dl>

### -field <b>ElementList</b>

<dd>
<p>Contains a structure of type <a href="..\ntddchgr\ns-ntddchgr--changer-element-list.md">CHANGER_ELEMENT_LIST</a> that specifies the element type and the number of elements. If the <b>Features0</b> member of the <a href="..\ntddchgr\ns-ntddchgr--get-changer-parameters.md">GET_CHANGER_PARAMETERS</a> structure is set to CHANGER_INIT_ELEM_STAT_WITH_RANGE, the changer supports initializing a range of elements. In this case, the element type can be <b>ChangerTransport</b>, <b>ChangerSlot</b>, <b>ChangerDrive</b>, or <b>ChangerIEPort</b> and <b>ElementList</b> can specify a number of elements to initialize. Otherwise, the element type must be <b>AllElements</b> and the number of elements is ignored. </p>
</dd>

### -field <b>BarCodeScan</b>

<dd>
<p>Instructs the changer driver, when <b>TRUE</b>, to initialize elements by scanning bar codes. When <b>FALSE</b>, the changer driver takes no action. This member is applicable only if the <b>Features0</b> member of GET_CHANGER_PARAMETERS is set to CHANGER_BAR_CODE_SCANNER_INSTALLED. If the changer has nonvolatile RAM, a bar code scan can serve as an optimization.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddchgr.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-initialize-element-status.md">IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changerinitializeelementstatus.md">ChangerInitializeElementStatus</a>
</dt>
<dt>
<a href="..\ntddchgr\ns-ntddchgr--get-changer-parameters.md">GET_CHANGER_PARAMETERS</a>
</dt>
<dt>
<a href="..\ntddchgr\ns-ntddchgr--changer-element-list.md">CHANGER_ELEMENT_LIST</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CHANGER_INITIALIZE_ELEMENT_STATUS structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
