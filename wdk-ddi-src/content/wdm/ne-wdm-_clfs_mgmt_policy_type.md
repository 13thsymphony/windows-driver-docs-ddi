---
UID: NE:wdm._CLFS_MGMT_POLICY_TYPE
title: "_CLFS_MGMT_POLICY_TYPE"
author: windows-driver-content
description: The CLFS_MGMT_POLICY_TYPE enumeration type identifies the type of a CLFS management policy.
old-location: kernel\clfs_mgmt_policy_type.htm
old-project: kernel
ms.assetid: 50e31ff1-07f2-4781-81f2-8db6e3cf9cc6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ClfsMgmtPolicyAutoGrow, CLFS_MGMT_POLICY_TYPE, PCLFS_MGMT_POLICY_TYPE, wdm/ClfsMgmtPolicyAutoShrink, ClfsMgmtPolicyMinimumSize, _CLFS_MGMT_POLICY_TYPE, wdm/ClfsMgmtPolicyAutoGrow, ClfsMgmtPolicyLogTail, wdm/ClfsMgmtPolicyInvalid, ClfsMgmtPolicyGrowthRate, ClfsMgmtPolicyNewContainerSize, wdm/ClfsMgmtPolicyNewContainerExtension, CLFS_MGMT_POLICY_TYPE enumeration [Kernel-Mode Driver Architecture], ClfsMgmtPolicyNewContainerExtension, ClfsMgmtPolicyNewContainerPrefix, kernel.clfs_mgmt_policy_type, *PCLFS_MGMT_POLICY_TYPE, wdm/ClfsMgmtPolicyNewContainerSize, wdm/CLFS_MGMT_POLICY_TYPE, ClfsMgmtPolicyMaximumSize, wdm/ClfsMgmtPolicyGrowthRate, sysenum_bae8275b-5f70-40fb-ae14-f803eaeb0a42.xml, wdm/ClfsMgmtPolicyMinimumSize, ClfsMgmtPolicyInvalid, PCLFS_MGMT_POLICY_TYPE enumeration pointer [Kernel-Mode Driver Architecture], wdm/ClfsMgmtPolicyLogTail, wdm/ClfsMgmtPolicyNewContainerPrefix, wdm/ClfsMgmtPolicyNewContainerSuffix, ClfsMgmtPolicyNewContainerSuffix, wdm/ClfsMgmtPolicyMaximumSize, ClfsMgmtPolicyAutoShrink, wdm/PCLFS_MGMT_POLICY_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	CLFS_MGMT_POLICY_TYPE
product: Windows
targetos: Windows
req.typenames: CLFS_MGMT_POLICY_TYPE, *PCLFS_MGMT_POLICY_TYPE
req.product: Windows 10 or later.
---

# _CLFS_MGMT_POLICY_TYPE Enumeration
The <b>CLFS_MGMT_POLICY_TYPE</b> enumeration type identifies the type of a CLFS management policy.

## Syntax
````
typedef enum _CLFS_MGMT_POLICY_TYPE { 
  ClfsMgmtPolicyMaximumSize            = 0,
  ClfsMgmtPolicyMinimumSize            = 1,
  ClfsMgmtPolicyNewContainerSize       = 2,
  ClfsMgmtPolicyGrowthRate             = 3,
  ClfsMgmtPolicyLogTail                = 4,
  ClfsMgmtPolicyAutoShrink             = 5,
  ClfsMgmtPolicyAutoGrow               = 6,
  ClfsMgmtPolicyNewContainerPrefix     = 7,
  ClfsMgmtPolicyNewContainerSuffix     = 8,
  ClfsMgmtPolicyNewContainerExtension  = 9,
  ClfsMgmtPolicyInvalid                = 10
} CLFS_MGMT_POLICY_TYPE, *PCLFS_MGMT_POLICY_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>ClfsMgmtPolicyAutoGrow</td>
                    <td>Indicates a policy that specifies whether the log should grow when fewer than two containers are free.</td>
                </tr>
            
                <tr>
                    <td>ClfsMgmtPolicyAutoShrink</td>
                    <td>Indicates a policy that specifies when the log will shrink based on the percentage of the log that is free.</td>
                </tr>
            
                <tr>
                    <td>ClfsMgmtPolicyGrowthRate</td>
                    <td>Indicates a policy that specifies how many new containers will be added to the log each time the log grows.</td>
                </tr>
            
                <tr>
                    <td>ClfsMgmtPolicyInvalid</td>
                    <td>Reserved for internal use.</td>
                </tr>
            
                <tr>
                    <td>ClfsMgmtPolicyLogTail</td>
                    <td>Indicates a policy that specifies how much free space will be requested when a client is notified to move its log tail.</td>
                </tr>
            
                <tr>
                    <td>ClfsMgmtPolicyMaximumSize</td>
                    <td>Indicates a policy that specifies the maximum size of a log.</td>
                </tr>
            
                <tr>
                    <td>ClfsMgmtPolicyMinimumSize</td>
                    <td>Indicates a policy that specifies the minimum size of a log.</td>
                </tr>
            
                <tr>
                    <td>ClfsMgmtPolicyNewContainerExtension</td>
                    <td>Indicates a policy that specifies an extension for the file name of each container.</td>
                </tr>
            
                <tr>
                    <td>ClfsMgmtPolicyNewContainerPrefix</td>
                    <td>Indicates a policy that specifies a prefix for the file name of each container, as well as the full path to the directory where the containers will be placed.</td>
                </tr>
            
                <tr>
                    <td>ClfsMgmtPolicyNewContainerSize</td>
                    <td>Indicates a policy that specifies the size of new containers that are created.</td>
                </tr>
            
                <tr>
                    <td>ClfsMgmtPolicyNewContainerSuffix</td>
                    <td>Indicates a policy that specifies a number to use as the starting suffix for container file names.</td>
                </tr>
</table>

    ## Remarks

        Each type of CLFS management policy corresponds to a specific interpretation of the <a href="..\wdm\ns-wdm-_clfs_mgmt_policy.md">CLFS_MGMT_POLICY</a> structure. The <b>PolicyType</b> member of the <b>CLFS_MGMT_POLICY</b> structure is a valid value of the <b>CLFS_MGMT_POLICY_TYPE</b> enumeration.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h) |

    ## See Also

        <a href="..\wdm\ns-wdm-_clfs_mgmt_policy.md">CLFS_MGMT_POLICY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CLFS_MGMT_POLICY_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>