﻿---
title: DeploymentBaseContext.RetryInterval Property  (Microsoft.Web.Deployment)
TOCTitle: RetryInterval Property
ms:assetid: P:Microsoft.Web.Deployment.DeploymentBaseContext.RetryInterval
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.web.deployment.deploymentbasecontext.retryinterval(v=VS.90)
ms:contentKeyID: 20208827
ms.date: 05/02/2012
mtps_version: v=VS.90
f1_keywords:
- Microsoft.Web.Deployment.DeploymentBaseContext.RetryInterval
- Microsoft.Web.Deployment.DeploymentBaseContext.get_RetryInterval
dev_langs:
- CSharp
- JScript
- VB
- c++
api_location:
- Microsoft.Web.Deployment.dll
api_name:
- Microsoft.Web.Deployment.DeploymentBaseContext.get_RetryInterval
- Microsoft.Web.Deployment.DeploymentBaseContext.RetryInterval
api_type:
- Managed
topic_type:
- apiref
- kbSyntax
product_family_name: VS
ROBOTS: INDEX,FOLLOW
---

# RetryInterval Property

Gets the interval, in milliseconds, to wait between retry attempts.

**Namespace:**  [Microsoft.Web.Deployment](microsoft-web-deployment-namespace.md)  
**Assembly:**  Microsoft.Web.Deployment (in Microsoft.Web.Deployment.dll)

## Syntax

``` vb
'Declaration
PublicReadOnlyPropertyRetryIntervalAsInteger
'Usage
DiminstanceAsDeploymentBaseContextDimvalueAsIntegervalue = instance.RetryInterval
```

``` csharp
publicintRetryInterval { get; }
```

``` c++
public:
propertyintRetryInterval {
    intget ();
}
```

``` jscript
function getRetryInterval () : int
```

#### Property Value

Type: [System. . :: . .Int32](https://msdn.microsoft.com/en-us/library/td2s409d\(v=vs.90\))  
The interval, in milliseconds, to wait between retry attempts.  

## Remarks

The default value is 1000 milliseconds.

## Permissions

  - Full trust for the immediate caller. This member cannot be used by partially trusted code. For more information, see [Using Libraries from Partially Trusted Code](https://msdn.microsoft.com/en-us/library/8skskf63\(v=vs.90\)).

## See Also

#### Reference

[DeploymentBaseContext Class](deploymentbasecontext-class-microsoft-web-deployment.md)

[Microsoft.Web.Deployment Namespace](microsoft-web-deployment-namespace.md)
