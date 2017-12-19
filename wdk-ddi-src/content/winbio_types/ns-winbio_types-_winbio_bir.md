---
UID: NS.WINBIO_TYPES._WINBIO_BIR
title: _WINBIO_BIR
author: windows-driver-content
description: The WINBIO_BIR structure is the root of the BIR (Biometric Information Record). It contains the size and offset of any other data elements in the BIR.
old-location: biometric\winbio_bir.htm
old-project: biometric
ms.assetid: 159d4767-b0e2-4d76-b23c-e078e13827dd
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WINBIO_BIR, WINBIO_BIR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winbio_types.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WINBIO_BIR
req.alt-loc: winbio_types.h
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
req.product: Windows 10 or later.
---

# _WINBIO_BIR structure



## -description
The WINBIO_BIR structure is the root of the BIR (Biometric Information Record). It contains the size and offset of any other data elements in the BIR.



## -syntax

````
typedef struct _WINBIO_BIR {
  WINBIO_BIR_DATA HeaderBlock;
  WINBIO_BIR_DATA StandardDataBlock;
  WINBIO_BIR_DATA VendorDataBlock;
  WINBIO_BIR_DATA SignatureBlock;
} WINBIO_BIR, *PWINBIO_BIR;
````


## -struct-fields

### -field HeaderBlock

A structure of type <a href="biometric.winbio_bir_data">WINBIO_BIR_DATA</a> that contains size and offset information for a standard biometric header. This member is required.


### -field StandardDataBlock

A structure of type <a href="biometric.winbio_bir_data">WINBIO_BIR_DATA</a> that contains size and offset information for a standard data block based on the ANSI 381 format. This member is optional. Set this member to 0,0 if you do not use it.


### -field VendorDataBlock

A structure of type <a href="biometric.winbio_bir_data">WINBIO_BIR_DATA</a> that contains size and offset information for a vendor-specific data block.  This member is optional. Set this member to 0,0 if you do not use it.


### -field SignatureBlock

A structure of type <a href="biometric.winbio_bir_data">WINBIO_BIR_DATA</a> that contains size and offset information for a signature block. This member is optional. Set this member to 0,0 if you do not use it.


## -remarks
The four WINBIO_BIR_DATA structures are contiguous and should be immediately followed by the actual data for each block.  Thus, the offset for the <i>HeaderBlock</i> will always be 4*(sizeof (WINBIO_BIR_DATA).  You can use the <a href="biometric.winbio_bir_header">WINBIO_BIR_HEADER</a> structure to provide the actual data of the header block.  

The offset of where the <i>StandardDataBlock</i> starts should be the offset of the HeaderBlock plus the size of the HeaderBlock.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Winbio_types.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="biometric.winbio_capture_data">WINBIO_CAPTURE_DATA</a>
</dt>
<dt>
<a href="biometric.winbio_data">WINBIO_DATA</a>
</dt>
<dt>
<a href="biometric.winbio_bir_data">WINBIO_BIR_DATA</a>
</dt>
<dt>
<a href="biometric.winbio_bir_header">WINBIO_BIR_HEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [biometric\biometric]:%20WINBIO_BIR structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

