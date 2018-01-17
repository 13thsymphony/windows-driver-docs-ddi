---
UID: NS:rilapitypes.RILSUBSCRIBERINFO
title: RILSUBSCRIBERINFO
author: windows-driver-content
description: This structure represents RILSUBSCRIBERINFO.
old-location: netvista\rilsubscriberinfo.htm
old-project: netvista
ms.assetid: b05a38c6-afc5-4dc1-8e51-ecf9d47e144e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSUBSCRIBERINFO, *LPRILSUBSCRIBERINFO, RILSUBSCRIBERINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILSUBSCRIBERINFO
req.alt-loc: rilapitypes.h
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
req.typenames: *LPRILSUBSCRIBERINFO, RILSUBSCRIBERINFO
req.product: Windows 10 or later.
---

# RILSUBSCRIBERINFO structure



## -description

## -syntax

````
struct RILSUBSCRIBERINFO {
  DWORD                    cbSize;
  DWORD                    dwParams;
  RILADDRESS               raAddress;
  WCHAR                    wszDescription[MAXLENGTH_DESCRIPTION];
  RILSUBSCRIBERINFOSERVICE dwService;
};
````


## -struct-fields

### -field cbSize

The size of the structure in bytes.


### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-rilsubscriberinfoparammask.md">RILSUBSCRIBERINFOPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.


### -field raAddress

Phone number of the subscriber line, of type <a href="..\rilapitypes\ne-rilapitypes-riladdresstype.md">RILADDRESSTYPE</a>.


### -field wszDescription

Text description of the subscriber line.


### -field dwService

Specifies the service related to the subscriber phone number, of type <a href="..\rilapitypes\ne-rilapitypes-rilsubscriberinfoservice.md">RILSUBSCRIBERINFOSERVICE</a>.


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILSUBSCRIBERINFO structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

