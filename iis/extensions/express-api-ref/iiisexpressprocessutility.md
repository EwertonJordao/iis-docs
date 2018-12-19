---
title: "IIISExpressProcessUtility | Microsoft Docs"
ms.custom: ""
ms.date: "10/07/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 514fec28-799c-464a-891b-d55bf892877c
caps.latest.revision: 6
manager: "wpickett"
---
# IIISExpressProcessUtility
Obtains information that describes how to locate, start, and stop IIS Express worker processes.  
  
## Syntax  
  
```cpp  
interface IIISExpressProcessUtility : IUnknown  
{  
    HRESULT  
    GetRunningProcessForSite(   
        [in] BSTR    bstrSite,   
        [in] BSTR    bstrApplication,   
        [in] BSTR    bstrApplicationPool,   
        [in] BSTR    bstrConfigPath,   
        [out, retval] DWORD * pdwPid  
    );  
  
    HRESULT  
    ConstructCommandLine(   
        [in] BSTR bstrSite,  
        [in] BSTR bstrApplication,  
        [in] BSTR bstrApplicationPool,   
        [in] BSTR bstrConfigPath,   
        [out, retval] BSTR * pbstrCommandLine  
    );  
  
    HRESULT  
    StopProcess(   
        [in] DWORD dwPid  
    );  
};  
  
```  
  
## See Also  
 [GetRunningProcessForSite](../../extenions\express-api-ref/getrunningprocessforsite.md)   
 [ConstructCommandLine](../../extenions\express-api-ref/constructcommandline.md)   
 [StopProcess](../../extenions\express-api-ref/stopprocess.md)