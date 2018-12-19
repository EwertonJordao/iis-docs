---
title: "IHttpResponse::GetErrorDescription Method | Microsoft Docs"
ms.custom: ""
ms.date: "10/07/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 11e42b08-ce5d-436b-aa14-05069dc4b5a8
caps.latest.revision: 10
author: "shirhatti"
manager: "wpickett"
---
# IHttpResponse::GetErrorDescription Method
Retrieves the custom error description.  
  
## Syntax  
  
```cpp  
virtual PCWSTR GetErrorDescription(  
   OUT DWORD* pcchDescription = NULL  
) = 0;  
```  
  
#### Parameters  
 `pcchDescription`  
 [OUT] A pointer to a `DWORD` value that contains the length, in characters, of the returned string.  
  
## Return Value  
 A pointer to a string that contains the custom error description.  
  
## Remarks  
 Developers use the `GetErrorDescription` method to retrieve the custom error description. IIS displays the custom error description as part of the detailed information that is sent to a Web client when IIS returns an error message.  
  
## Example  
 The following code example demonstrates how to create an HTTP module that performs the following tasks:  
  
1.  Retrieves a pointer to an [IHttpResponse](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpresponse-interface.md) interface by using the [IHttpContext::GetResponse](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpcontext-getresponse-method.md) method.  
  
2.  Retrieves the current HTTP status code by using the [IHttpResponse::GetStatus](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpresponse-getstatus-method.md) method.  
  
3.  If the current HTTP status code is a 404.0 error, retrieves the current custom error description by using the `GetErrorDescription` method.  
  
4.  If no custom error description is currently defined, sets the custom error description by using the [IHttpResponse::SetErrorDescription](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpresponse-seterrordescription-method.md) method.  
  
<!-- TODO: review snippet reference  [!CODE [IHttpResponseSetErrorDescription#1](IHttpResponseSetErrorDescription#1)]  -->  
  
 Your module must export the [RegisterModule](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/pfn-registermodule-function.md) function. You can export this function by creating a module definition (.def) file for your project, or you can compile the module by using the `/EXPORT:RegisterModule` switch. For more information, see [Walkthrough: Creating a Request-Level HTTP Module By Using Native Code](../../../webdevelopment-reference\native-code-development-overview\native-code-dev-overview/walkthrough-creating-a-request-level-http-module-by-using-native-code.md).  
  
 You can optionally compile the code by using the `__stdcall (/Gz)` calling convention instead of explicitly declaring the calling convention for each function.  
  
## Requirements  
  
|Type|Description|  
|----------|-----------------|  
|Client|-   [!INCLUDE[iis70](../../../wmi-provider/includes/iis70-md.md)] on [!INCLUDE[winvista](../../../wmi-provider/includes/winvista-md.md)]<br />-   [!INCLUDE[iis75](../../../wmi-provider/includes/iis75-md.md)] on [!INCLUDE[win7](../../../wmi-provider/includes/win7-md.md)]<br />-   [!INCLUDE[iis80](../../../wmi-provider/includes/iis80-md.md)] on [!INCLUDE[win8](../../../wmi-provider/includes/win8-md.md)]<br />-   [!INCLUDE[iis100](../../../wmi-provider/includes/iis100-md.md)] on [!INCLUDE[win10](../../../wmi-provider/includes/win10-md.md)]|  
|Server|-   [!INCLUDE[iis70](../../../wmi-provider/includes/iis70-md.md)] on [!INCLUDE[winsrv2008](../../../wmi-provider/includes/winsrv2008-md.md)]<br />-   [!INCLUDE[iis75](../../../wmi-provider/includes/iis75-md.md)] on [!INCLUDE[winsrv2008r2](../../../wmi-provider/includes/winsrv2008r2-md.md)]<br />-   [!INCLUDE[iis80](../../../wmi-provider/includes/iis80-md.md)] on [!INCLUDE[winsrv2012](../../../wmi-provider/includes/winsrv2012-md.md)]<br />-   [!INCLUDE[iis85](../../../wmi-provider/includes/iis85-md.md)] on [!INCLUDE[winsrv2012r2](../../../wmi-provider/includes/winsrv2012r2-md.md)]<br />-   [!INCLUDE[iis100](../../../wmi-provider/includes/iis100-md.md)] on [!INCLUDE[winsrv2016](../../../wmi-provider/includes/winsrv2016-md.md)]|  
|Product|-   [!INCLUDE[iis70](../../../wmi-provider/includes/iis70-md.md)], [!INCLUDE[iis75](../../../wmi-provider/includes/iis75-md.md)], [!INCLUDE[iis80](../../../wmi-provider/includes/iis80-md.md)], [!INCLUDE[iis85](../../../wmi-provider/includes/iis85-md.md)], [!INCLUDE[iis100](../../../wmi-provider/includes/iis100-md.md)]<br />-   [!INCLUDE[iisexp75](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/includes/iisexp75-md.md)], [!INCLUDE[iisexp80](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/includes/iisexp80-md.md)], [!INCLUDE[iisexp100](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/includes/iisexp100-md.md)]|  
|Header|Httpserv.h|  
  
## See Also  
 [IHttpResponse Interface](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpresponse-interface.md)   
 [IHttpResponse::SetErrorDescription Method](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpresponse-seterrordescription-method.md)