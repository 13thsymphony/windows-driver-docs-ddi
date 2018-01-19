---
UID : NS:wlanihv._DOT11EXT_IHV_UI_REQUEST
title : _DOT11EXT_IHV_UI_REQUEST
author : windows-driver-content
description : Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location : netvista\dot11ext_ihv_ui_request.htm
old-project : netvista
ms.assetid : 028e3445-320a-41c8-9577-219f9fbabe40
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _DOT11EXT_IHV_UI_REQUEST, *PDOT11EXT_IHV_UI_REQUEST, DOT11EXT_IHV_UI_REQUEST
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wlanihv.h
req.include-header : Wlanihv.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DOT11EXT_IHV_UI_REQUEST
req.alt-loc : wlanihv.h
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
req.typenames : "*PDOT11EXT_IHV_UI_REQUEST, DOT11EXT_IHV_UI_REQUEST"
req.product : Windows 10 or later.
---

# _DOT11EXT_IHV_UI_REQUEST structure


## Syntax
````
typedef struct _DOT11EXT_IHV_UI_REQUEST {
  DWORD dwSessionId;
  GUID  guidUIRequest;
  CLSID UIPageClsid;
  DWORD dwByteCount;
  BYTE  *pvUIRequest;
} DOT11EXT_IHV_UI_REQUEST, *PDOT11EXT_IHV_UI_REQUEST;
````

## Members

        
            `dwByteCount`

            The length, in bytes, within the buffer referenced through the 
     <b>pvUIRequest</b> member.
        
            `dwSessionId`

            The session identifier (ID) of the current user.
        
            `guidUIRequest`

            A globally unique ID (GUID) which identifies the UI request.
        
            `pvUIRequest`

            A pointer to a buffer that contains the request data in a format defined by the independent
     hardware vendor (IHV).
        
            `UIPageClsid`

            The 
     <b>IWizardExtension</b> COM class ID (CLSID) of the target UI page that will handle this request. For
     more information about the 
     <b>IWizardExtension</b> COM interface, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=56607">IWizardExtension COM Interface</a>.

    ## Remarks
        The IHV Extensions DLL can issue requests to the IHV UI extensions DLL to interact with the user for
    input to network UI extensions defined by the IHV. The IHV Extensions DLL initiates these requests
    through calls to the 
    <a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">Dot11ExtSendUIRequest</a> or 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_query_ui_request.md">
    Dot11ExtIhvQueryUIRequest</a> functions.

For each UI request, the DLL must format a DOT11EXT_IHV_UI_REQUEST structure to define the request,
    and must set the 
    <b>guidUIRequest</b> member of this structure to a GUID value that uniquely identifies the UI request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wlanihv.h (include Wlanihv.h) |

    ## See Also

        <dl>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_is_ui_request_pending.md">
   Dot11ExtIhvIsUIRequestPending</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_query_ui_request.md">Dot11ExtIhvQueryUIRequest</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_send_ui_request.md">Dot11ExtSendUIRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_IHV_UI_REQUEST structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>