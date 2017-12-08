---
UID: NS.d3dkmddi._DXGK_SEGMENTBANKPREFERENCE
title: DXGK_SEGMENTBANKPREFERENCE
author: windows-driver-content
description: The DXGK_SEGMENTBANKPREFERENCE structure describes bank preferences for paging in an allocation.
old-location: display\dxgk_segmentbankpreference.htm
old-project: display
ms.assetid: ff292137-4d95-4388-aae9-f6436b403c6a
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_SEGMENTBANKPREFERENCE, DXGK_SEGMENTBANKPREFERENCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_SEGMENTBANKPREFERENCE
req.alt-loc: d3dkmddi.h
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
req.iface: 
---

# DXGK_SEGMENTBANKPREFERENCE structure



## -description
<p>The <b>DXGK_SEGMENTBANKPREFERENCE</b> structure describes bank preferences for paging in an allocation.</p>


## -syntax

````
typedef struct _DXGK_SEGMENTBANKPREFERENCE {
  union {
    struct {
      UINT Bank0  :7;
      UINT Direction0  :1;
      UINT Bank1  :7;
      UINT Direction1  :1;
      UINT Bank2  :7;
      UINT Direction2  :1;
      UINT Bank3  :7;
      UINT Direction3  :1;
    };
    UINT Value;
  };
} DXGK_SEGMENTBANKPREFERENCE;
````


## -struct-fields
<dl>

### -field Bank0

<dd>
<p>[out] The identifier of the highest priority preferred bank, or 0 if no preference is required. Valid values are from 1 to 127.</p>
<p>This member is equivalent to the first 7 bits of the 32-bit <b>Value</b> member (0x0000007F). </p>
</dd>

### -field Direction0

<dd>
<p>[out] The direction in which <b>Bank0</b> should be scanned to locate a free area of memory. A value of 0 indicates a bottom-up search (that is, low address to high address), and a value of 1 indicates a top-bottom search (that is, high address to low address).</p>
<p>This member is equivalent to the eighth bit of the 32-bit <b>Value</b> member (0x00000080). </p>
</dd>

### -field Bank1

<dd>
<p>[out] The identifier of the next highest priority preferred bank, or 0 if no preference is required. Valid values are from 1 to 127.</p>
<p>This member is equivalent to bits 9 through 15 of the 32-bit <b>Value</b> member (0x00007F00). </p>
</dd>

### -field Direction1

<dd>
<p>[out] The direction in which <b>Bank1</b> should be scanned to locate a free hole of memory. A value of 0 indicates a bottom-up search (that is, low address to high address), and a value of 1 indicates a top-bottom search (that is, high address to low address).</p>
<p>This member is equivalent to the sixteenth bit of the 32-bit <b>Value</b> member (0x00008000). </p>
</dd>

### -field Bank2

<dd>
<p>[out] The identifier of the next highest priority preferred bank, or 0 if no preference is required. Valid values are from 1 to 127.</p>
<p>This member is equivalent to bits 17 through 23 of the 32-bit <b>Value</b> member (0x007F0000). </p>
</dd>

### -field Direction2

<dd>
<p>[out] The direction in which <b>Bank2</b> should be scanned to locate a free hole of memory. A value of 0 indicates a bottom-up search (that is, low address to high address), and a value of 1 indicates a top-bottom search (that is, high address to low address).</p>
<p>This member is equivalent to the twenty-fourth bit of the 32-bit <b>Value</b> member (0x00800000). </p>
</dd>

### -field Bank3

<dd>
<p>[out] The identifier of the next highest priority preferred bank, or 0 if no preference is required. Valid values are from 1 to 127.</p>
<p>This member is equivalent to bits 25 through 31 of the 32-bit <b>Value</b> member (0x7F000000). </p>
</dd>

### -field Direction3

<dd>
<p>[out] The direction in which <b>Bank3</b> should be scanned to locate a free hole of memory. A value of 0 indicates a bottom-up search (that is, low address to high address), and a value of 1 indicates a top-bottom search (that is, high address to low address).</p>
<p>This member is equivalent to the thirty-secondbit of the 32-bit <b>Value</b> member (0x80000000). </p>
</dd>

### -field Value

<dd>
<p>[out] A member in the union that DXGK_SEGMENTBANKPREFERENCE contains that can hold a 32-bit value that identifies bank preferences.</p>
</dd>
</dl>

## -remarks
<p>The display miniport driver can indicate up to four bank preferences in the <b>HintedBank</b> member of a <a href="..\d3dkmddi\ns-d3dkmddi--dxgk-allocationinfo.md">DXGK_ALLOCATIONINFO</a> structure when the driver's <a href="display.dxgkddicreateallocation">DxgkDdiCreateAllocation</a> function is called. Preferred-bank identifiers are one-based (that is, the first bank has an identifier of one). An identifier of zero indicates that the driver has no preference. The highest priority preference is specified in the <b>Bank0</b> member; the lowest priority preference is specified in the <b>Bank3</b> member. The driver can specify less than four preferences by setting the lower priority preferences of bank identifiers to zero. For example, the driver can specify two preferences by setting <b>Bank0</b> and <b>Bank1</b> to valid identifiers and <b>Bank2</b> and <b>Bank3</b> to zero. The driver can use each <b>Direction</b><i>X</i> member to specify the scanning direction for each bank preference independently. </p>

<p> The video memory manager  allocates resources from  preferred segments that the <b>PreferredSegment</b> member of DXGK_ALLOCATIONINFO specifies. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi--dxgk-allocationlist.md">DXGK_ALLOCATIONLIST</a>
</dt>
<dt>
<a href="display.dxgk_segmentpreference">DXGK_SEGMENTPREFERENCE</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi--dxgk-allocationinfo.md">DXGK_ALLOCATIONINFO</a>
</dt>
<dt>
<a href="display.dxgkddicreateallocation">DxgkDdiCreateAllocation</a>
</dt>
<dt>
<a href="display.dxgkddirender">DxgkDdiRender</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_SEGMENTBANKPREFERENCE structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
