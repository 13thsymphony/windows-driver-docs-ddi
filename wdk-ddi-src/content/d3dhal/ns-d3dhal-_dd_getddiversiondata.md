---
UID: NS:d3dhal._DD_GETDDIVERSIONDATA
title: "_DD_GETDDIVERSIONDATA"
author: windows-driver-content
description: DirectX 9.0 and later versions only. DD_GETDDIVERSIONDATA is the data structure pointed to by the lpvData field of DD_GETDRIVERINFODATA for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETDDIVERSION.
old-location: display\dd_getddiversiondata.htm
old-project: display
ms.assetid: 4f96ef86-1155-4483-915e-706cc18c3bca
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_DD_GETDDIVERSIONDATA, display.dd_getddiversiondata, DD_GETDDIVERSIONDATA structure [Display Devices], DD_GETDDIVERSIONDATA, d3dstrct_c15b9015-5e12-41bc-a44b-751f2a8813e9.xml, d3dhal/DD_GETDDIVERSIONDATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dhal.h
apiname:
-	DD_GETDDIVERSIONDATA
product: Windows
targetos: Windows
req.typenames: DD_GETDDIVERSIONDATA
---

# _DD_GETDDIVERSIONDATA structure
DirectX 9.0 and later versions only.
   

DD_GETDDIVERSIONDATA is the data structure pointed to by the <b>lpvData</b> field of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a> for DD_GETDRIVERINFO2DATA queries with the type D3DGDI2_TYPE_GETDDIVERSION.

## Syntax
````
typedef struct _DD_GETDDIVERSIONDATA {
  DD_GETDRIVERINFO2DATA gdi2;
  DWORD                 dwDXVersion;
  DWORD                 dwDDIVersion;
} DD_GETDDIVERSIONDATA;
````

## Members


`dwDDIVersion`

Receives the version of the DDI that the driver supports.

`dwDXVersion`

Specifies the version of the DirectX runtime that makes the request. For example, the DirectX 9.0 runtime specifies 9.

`gdi2`

Specifies a <a href="..\d3dhal\ns-d3dhal-_dd_getdriverinfo2data.md">DD_GETDRIVERINFO2DATA</a> structure that contains the <b>GetDriverInfo2</b> data for the query.

## Remarks
During the development phase of a version of DirectX, whenever a significant change is made to the Driver Development Kit (DDK) headers, the version number of the DDI is updated. Thereafter, a display driver must report this updated DDI version in order to be run as the most-recent-version DirectX driver. If the driver does not report this updated DDI version, the runtime determines that the driver is the prior version of DirectX and handles the driver accordingly. 

For example, suppose that a hardware vendor builds his display driver with a pre-released version of the DirectX 9.0 DDK and then attempts to ship his driver as a DirectX 9.0 version. If the DDI version number is updated in the final version of DirectX 9.0, the DirectX 9.0 runtime subsequently treats this driver as a DirectX 8.0 version driver instead.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dhal.h (include D3dhal.h) |

## See Also

<a href="..\d3dhal\ns-d3dhal-_dd_getdriverinfo2data.md">DD_GETDRIVERINFO2DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551550">DD_GETDRIVERINFODATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DD_GETDDIVERSIONDATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>