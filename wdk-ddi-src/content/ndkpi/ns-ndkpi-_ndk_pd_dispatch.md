---
UID : NS:ndkpi._NDK_PD_DISPATCH
title : _NDK_PD_DISPATCH
author : windows-driver-content
description : The NDK_PD_DISPATCH structure specifies dispatch function entry points for the NDK protection domain (PD) object.
old-location : netvista\ndk_pd_dispatch.htm
old-project : netvista
ms.assetid : 3BAD6CF9-8DCD-470F-9C2E-C7C9C0B29ADA
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _NDK_PD_DISPATCH, NDK_PD_DISPATCH
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ndkpi.h
req.include-header : Ndkpi.h
req.target-type : Windows
req.target-min-winverclnt : None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NDK_PD_DISPATCH
req.alt-loc : ndkpi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <=DISPATCH_LEVEL
req.typenames : NDK_PD_DISPATCH
---

# _NDK_PD_DISPATCH structure
The <b>NDK_PD_DISPATCH</b> structure specifies dispatch function entry points for the NDK protection domain (PD) object.

## Syntax
````
typedef struct _NDK_PD_DISPATCH {
  NDK_FN_CLOSE_OBJECT                       NdkClosePd;
  NDK_FN_QUERY_EXTENSION_INTERFACE          NdkQueryExtension;
  NDK_FN_CREATE_MR                          NdkCreateMr;
  NDK_FN_CREATE_MW                          NdkCreateMw;
  NDK_FN_CREATE_SRQ                         NdkCreateSrq;
  NDK_FN_CREATE_QP                          NdkCreateQp;
  NDK_FN_CREATE_QP_WITH_SRQ                 NdkCreateQpWithSrq;
  NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN NdkGetPrivilegedMemoryRegionToken;
} NDK_PD_DISPATCH;
````

## Members

        
            `NdkClosePd`

            The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a> dispatch function.
        
            `NdkCreateMr`

            The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_create_mr.md">NDK_FN_CREATE_MR</a> dispatch function.
        
            `NdkCreateMw`

            The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_create_mw.md">NDK_FN_CREATE_MW</a> dispatch function.
        
            `NdkCreateQp`

            The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_create_qp.md">NDK_FN_CREATE_QP</a> dispatch function.
        
            `NdkCreateQpWithSrq`

            The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_create_qp_with_srq.md">NDK_FN_CREATE_QP_WITH_SRQ</a> dispatch function.
        
            `NdkCreateSrq`

            The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_create_srq.md">NDK_FN_CREATE_SRQ</a> dispatch function.
        
            `NdkGetPrivilegedMemoryRegionToken`

            The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_get_privileged_memory_region_token.md">NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN</a> dispatch function.
        
            `NdkQueryExtension`

            The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.

    ## Remarks
        The <b>NDK_PD_DISPATCH</b> structure is used in the <a href="..\ndkpi\ns-ndkpi-_ndk_pd.md">NDK_PD</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndkpi.h (include Ndkpi.h) |

    ## See Also

        <dl>
<dt>
<a href="..\ndkpi\ns-ndkpi-_ndk_pd.md">NDK_PD</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_mr.md">NDK_FN_CREATE_MR</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_mw.md">NDK_FN_CREATE_MW</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_qp.md">NDK_FN_CREATE_QP</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_qp_with_srq.md">NDK_FN_CREATE_QP_WITH_SRQ</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_srq.md">NDK_FN_CREATE_SRQ</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_privileged_memory_region_token.md">NDK_FN_GET_PRIVILEGED_MEMORY_REGION_TOKEN</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_PD_DISPATCH structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>