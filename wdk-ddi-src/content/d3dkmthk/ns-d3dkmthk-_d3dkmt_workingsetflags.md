---
UID : NS:d3dkmthk._D3DKMT_WORKINGSETFLAGS
title : _D3DKMT_WORKINGSETFLAGS
author : windows-driver-content
description : The D3DKMT_WORKINGSETFLAGS structure identifies working-set properties of the display miniport driver that the OpenGL installable client driver (ICD) obtains by calling the D3DKMTQueryAdapterInfo function.
old-location : display\d3dkmt_workingsetflags.htm
old-project : display
ms.assetid : 05dddebc-2a30-4cc5-b905-9ee4ebf8d00e
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.d3dkmt_workingsetflags, D3DKMT_WORKINGSETFLAGS, _D3DKMT_WORKINGSETFLAGS, D3DKMT_WORKINGSETFLAGS structure [Display Devices], OpenGL_Structs_4ce8b8d1-7f35-45b4-8b01-154a9a8eda00.xml, d3dkmthk/D3DKMT_WORKINGSETFLAGS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmthk.h
req.include-header : D3dkmthk.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3DKMT_WORKINGSETFLAGS
---

# _D3DKMT_WORKINGSETFLAGS structure
The D3DKMT_WORKINGSETFLAGS structure identifies working-set properties of the display miniport driver that the OpenGL installable client driver (ICD) obtains by calling the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a> function.

## Syntax
````
typedef struct _D3DKMT_WORKINGSETFLAGS {
  UINT UseDefault  :1;
  UINT Reserved  :31;
} D3DKMT_WORKINGSETFLAGS;
````

## Members


`Reserved`

This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 31 bits (0xFFFFFFFE) of a 32-bit value to zeros.

`UseDefault`

A UINT value that specifies whether the display miniport driver uses the default working set.

Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_workingsetinfo.md">D3DKMT_WORKINGSETINFO</a>

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryadapterinfo.md">D3DKMTQueryAdapterInfo</a>

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_queryadapterinfo.md">D3DKMT_QUERYADAPTERINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_WORKINGSETFLAGS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>