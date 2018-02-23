---
UID: NS:d3dukmdt._D3DDDI_SYNCHRONIZATIONOBJECTINFO
title: "_D3DDDI_SYNCHRONIZATIONOBJECTINFO"
author: windows-driver-content
description: The D3DDDI_SYNCHRONIZATIONOBJECTINFO structure contains information about a synchronization object.
old-location: display\d3dddi_synchronizationobjectinfo.htm
old-project: display
ms.assetid: 786934f5-b0ec-4ee9-8bf0-f32b64295b96
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "_D3DDDI_SYNCHRONIZATIONOBJECTINFO, display.d3dddi_synchronizationobjectinfo, D3D_other_Structs_86538364-14f8-4e40-bf0e-2e9f836729b8.xml, D3DDDI_SYNCHRONIZATIONOBJECTINFO structure [Display Devices], D3DDDI_SYNCHRONIZATIONOBJECTINFO, d3dukmdt/D3DDDI_SYNCHRONIZATIONOBJECTINFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dukmdt.h
apiname:
-	D3DDDI_SYNCHRONIZATIONOBJECTINFO
product: Windows
targetos: Windows
req.typenames: D3DDDI_SYNCHRONIZATIONOBJECTINFO
---

# _D3DDDI_SYNCHRONIZATIONOBJECTINFO structure
The D3DDDI_SYNCHRONIZATIONOBJECTINFO structure contains information about a synchronization object.

## Syntax
````
typedef struct _D3DDDI_SYNCHRONIZATIONOBJECTINFO {
  D3DDDI_SYNCHRONIZATIONOBJECT_TYPE Type;
  union {
    struct {
      BOOL InitialState;
    } SynchronizationMutex;
    struct {
      UINT MaxCount;
      UINT InitialCount;
    } Semaphore;
    struct {
      UINT Reserved[16];
    } Reserved;
  };
} D3DDDI_SYNCHRONIZATIONOBJECTINFO;
````

## Members


`Type`

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_synchronizationobject_type.md">D3DDDI_SYNCHRONIZATIONOBJECT_TYPE</a>-typed value that indicates the type of synchronization object.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dukmdt.h (include D3dumddi.h, D3dkmddi.h) |

## See Also

<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_synchronizationobject_type.md">D3DDDI_SYNCHRONIZATIONOBJECT_TYPE</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_createsynchronizationobject.md">D3DDDICB_CREATESYNCHRONIZATIONOBJECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_SYNCHRONIZATIONOBJECTINFO structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>