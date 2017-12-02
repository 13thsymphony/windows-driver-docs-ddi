---
UID: NS.spb.SPB_TRANSFER_LIST
title: SPB_TRANSFER_LIST
author: windows-driver-content
description: The SPB_TRANSFER_LIST structure describes an I/O transfer sequence.
old-location: spb\spb_transfer_list.htm
old-project: SPB
ms.assetid: DC4E165B-4D3A-4C5F-9B6F-8CB825BAF4FD
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: SPB_TRANSFER_LIST,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: spb.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SPB_TRANSFER_LIST
req.alt-loc: Spb.h
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
req.product: Windows 10 or later.
---

# SPB_TRANSFER_LIST structure



## -description
<p>The <b>SPB_TRANSFER_LIST</b> structure describes an <a href="https://msdn.microsoft.com/7415DB28-5E93-4F47-B169-7C652969D4C7">I/O transfer sequence</a>.</p>


## -syntax

````
typedef struct _SPB_TRANSFER_LIST {
  ULONG                   Size;
  ULONG                   Reserved;
  ULONG                   TransferCount;
  SPB_TRANSFER_LIST_ENTRY Transfers[1];
} SPB_TRANSFER_LIST, *PSPB_TRANSFER_LIST;
````


## -struct-fields
<dl>

### -field Size

<dd>
<p>The size, in bytes, of the <b>SPB_TRANSFER_LIST</b> structure. This size value does not include any <b>Transfers</b> array elements that might follow this structure. If new members are added to future versions of this structure, the <b>Size</b> value can be used to determine which version of the <b>SPB_TRANSFER_LIST</b> structure is being used.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved for use by the operating system. Set to zero.</p>
</dd>

### -field TransferCount

<dd>
<p>The number of elements in the <b>Transfers</b> array. This array contains a minimum of one element.</p>
</dd>

### -field Transfers

<dd>
<p>This member is the first element in an array of <a href="https://msdn.microsoft.com/library/windows/hardware/hh406223">SPB_TRANSFER_LIST_ENTRY</a> structures.  Each array element describes an individual transfer in the I/O transfer sequence. If the array contains more than one element, the additional array elements immediately follow the <b>SPB_TRANSFER_LIST</b> structure in memory. The transfers are performed in the order in which they appear in the array, starting with the first element.</p>
</dd>
</dl>

## -remarks
<p>The input buffer for an <a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a> request begins with an <b>SPB_TRANSFER_LIST</b> structure. The first transfer in the requested I/O transfer sequence is specified in the <b>Transfers</b> member of this structure. If the sequence contains more than one transfer, the array elements that describe the additional transfers immediately follow the <b>SPB_TRANSFER_LIST</b> structure.</p>

<p>The input buffer for an <a href="https://msdn.microsoft.com/library/windows/hardware/hh974774">IOCTL_SPB_FULL_DUPLEX</a> request begins with an <b>SPB_TRANSFER_LIST</b> structure. The <b>SPB_TRANSFER_LIST</b> structure for this request always specifies two buffers. The first buffer, which is described by the <b>Transfers</b> member of this structure, contains the data to write to the device. The second buffer, which is described by an array element that immediately follows the <b>SPB_TRANSFER_LIST</b> structure, is used to hold the data read from the device.</p>

<p>If your SPB controller driver supports custom I/O control (IOCTL) requests that use input or output buffers, use the <b>SPB_TRANSFER_LIST</b> structure to describe these buffers. For more information, see <a href="https://msdn.microsoft.com/577122CC-D1F8-41C5-BE77-A22FC8516B82">Using the SPB_TRANSFER_LIST Structure for Custom IOCTLs</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Spb.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450857">IOCTL_SPB_EXECUTE_SEQUENCE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh974774">IOCTL_SPB_FULL_DUPLEX</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406223">SPB_TRANSFER_LIST_ENTRY</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SPB_TRANSFER_LIST structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
