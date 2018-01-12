---
UID: NS:d3dkmdt._DXGKMDT_OPM_OMAC
title: _DXGKMDT_OPM_OMAC
author: windows-driver-content
description: The DXGKMDT_OPM_OMAC structure contains a One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) for message authenticity.
old-location: display\dxgkmdt_opm_omac.htm
old-project: display
ms.assetid: caa64a32-3772-45b5-898a-78dc51b7f24b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGKMDT_OPM_OMAC, DXGKMDT_OPM_OMAC, *PDXGKMDT_OPM_OMAC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKMDT_OPM_OMAC
req.alt-loc: d3dkmdt.h
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
req.typenames: DXGKMDT_OPM_OMAC, *PDXGKMDT_OPM_OMAC
---

# _DXGKMDT_OPM_OMAC structure



## -description
The DXGKMDT_OPM_OMAC structure contains a One-key Cipher Block Chaining (CBC)-mode message authentication code (OMAC) for message authenticity.



## -syntax

````
typedef struct _DXGKMDT_OPM_OMAC {
  BYTE abOMAC[DXGKMDT_OPM_OMAC_SIZE];
} DXGKMDT_OPM_OMAC, *PDXGKMDT_OPM_OMAC;
````


## -struct-fields

### -field abOMAC

A 16-byte array that comprises the OMAC.


## -remarks
For more information about OMAC, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70417">OMAC-1 algorithm</a>. 

The OMAC-1 parameters that OPM and COPP use are:

<i>E</i> = AES (Advanced Encryption Standard)

<i>t</i> = 128 bits

<i>K</i> = The 128-bit key that the display miniport driver receives when <a href="..\dispmprt\nc-dispmprt-dxgkddi_opm_set_signing_key_and_sequence_numbers.md">DxgkDdiOPMSetSigningKeyAndSequenceNumbers</a> is called.

<i>n</i> = 128 bits 

For information about AES, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=70411">RSA Laboratories</a> website. 


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_configure_parameters.md">DXGKMDT_OPM_CONFIGURE_PARAMETERS</a>
</dt>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters.md">DXGKMDT_OPM_GET_INFO_PARAMETERS</a>
</dt>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt-_dxgkmdt_opm_requested_information.md">DXGKMDT_OPM_REQUESTED_INFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKMDT_OPM_OMAC structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

