---
UID : NS:d3dkmthk._D3DKMT_GETPRESENTHISTORY
title : _D3DKMT_GETPRESENTHISTORY
author : windows-driver-content
description : The D3DKMT_GETPRESENTHISTORY structure describes the state of copying history.
old-location : display\d3dkmt_getpresenthistory.htm
old-project : display
ms.assetid : 6d9b0473-544f-43aa-9358-ec51d84d45d9
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _D3DKMT_GETPRESENTHISTORY, D3DKMT_GETPRESENTHISTORY
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
req.alt-api : D3DKMT_GETPRESENTHISTORY
req.alt-loc : d3dkmthk.h
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
req.typenames : D3DKMT_GETPRESENTHISTORY
---

# _D3DKMT_GETPRESENTHISTORY structure
The D3DKMT_GETPRESENTHISTORY structure describes the state of copying history.

## Syntax
````
typedef struct _D3DKMT_GETPRESENTHISTORY {
  D3DKMT_HANDLE              hAdapter;
  UINT                       ProvidedSize;
  UINT                       WrittenSize;
  D3DKMT_PRESENTHISTORYTOKEN *pTokens;
  UINT                       NumTokens;
} D3DKMT_GETPRESENTHISTORY;
````

## Members

        
            `hAdapter`

            [in] The handle to the graphics adapter.
        
            `NumTokens`

            Supported in Windows 7 and later versions.

[out] The number of tokens that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetpresenthistory.md">D3DKMTGetPresentHistory</a> function copies to the buffer that the <b>pTokens</b> member points to.
        
            `ProvidedSize`

            Supported in Windows 7 and later versions.

[in] The size, in bytes, of the provided buffer that the <b>pTokens</b> member points to.
        
            `pTokens`

            Supported in Windows 7 and later versions.

[in/out] A pointer to the buffer that receives the tokens. Each token is described by a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_presenthistorytoken.md">D3DKMT_PRESENTHISTORYTOKEN</a> structure.
        
            `WrittenSize`

            Supported in Windows 7 and later versions.

[out] The size, in bytes, that the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetpresenthistory.md">D3DKMTGetPresentHistory</a> function copies to the buffer that the <b>pTokens</b> member points to or the required size for first token.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

    ## See Also

        <dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_presenthistorytoken.md">D3DKMT_PRESENTHISTORYTOKEN</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetpresenthistory.md">D3DKMTGetPresentHistory</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_GETPRESENTHISTORY structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>