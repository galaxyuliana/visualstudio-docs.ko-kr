---
title: 'CA3147: ValidateAntiForgeryToken을 사용하여 동사 처리기를 표시하세요.'
ms.date: 08/08/2018
ms.prod: visual-studio-dev15
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 630d16b17f687842574348d86c1591a5433d9bfa
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55037147"
---
# <a name="ca3147-mark-verb-handlers-with-validateantiforgerytoken"></a>CA3147: ValidateAntiForgeryToken을 사용하여 동사 처리기를 표시하세요.

|||
|-|-|
|TypeName|MarkVerbHandlersWithValidateAntiForgeryToken|
|CheckId|CA3147|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

ASP.NET MVC 컨트롤러 동작 메서드를 사용 하 여 표시 되지 않습니다 [ValidateAntiForgeryTokenAttribute](/previous-versions/aspnet/web-frameworks/dd492108(v=vs.118)), 또는 같은 HTTP 동사를 지정 하는 특성 [HttpGetAttribute](/previous-versions/aspnet/web-frameworks/ee470993(v%3dvs.118)) 또는 [ AcceptVerbsAttribute](/previous-versions/aspnet/web-frameworks/dd470553%28v%3dvs.118%29)합니다.

## <a name="rule-description"></a>규칙 설명

ASP.NET MVC 컨트롤러를 디자인할 때 교차 사이트 요청 위조 공격 주의 해야 합니다. 교차 사이트 요청 위조 공격을 ASP.NET MVC 컨트롤러에 인증된 된 사용자를 악성 요청을 보낼 수 있습니다. 자세한 내용은 [ASP.NET MVC 및 웹 페이지에서 XSRF/CSRF 방지](/aspnet/mvc/overview/security/xsrfcsrf-prevention-in-aspnet-mvc-and-web-pages)합니다.

이 규칙에서는 ASP.NET MVC 컨트롤러 작업 메서드 중 하나:

- 있어야 합니다 [ValidateAntiforgeryTokenAttribute](/previous-versions/aspnet/web-frameworks/dd492108%28v%3dvs.118%29) HTTP GET을 포함 하지 않고 허용 된 HTTP 동사를 지정 합니다.

- 허용 된 동사를로 HTTP GET을 지정 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

- HTTP GET 요청을 처리 하 고 잠재적으로 해로운 부작용이 없는 ASP.NET MVC 컨트롤러 작업에 대 한 추가 [HttpGetAttribute](/previous-versions/aspnet/web-frameworks/ee470993%28v%3dvs.118%29) 방법입니다.

   ASP.NET MVC 컨트롤러 작업이 HTTP GET을 처리 하는 요청 하 고 중요 한 데이터를 수정 하는 등 잠재적으로 해로운 의도 하지 않은 경우 응용 프로그램은 교차 사이트 요청 위조 공격에 취약 합니다.  HTTP POST, PUT 또는 DELETE 요청에만 중요 한 작업을 수행할 수 있도록 응용 프로그램을 다시 디자인 해야 합니다.

- HTTP POST를 처리 하는 ASP.NET MVC 컨트롤러 작업에 대 한 PUT 또는 DELETE 요청을 추가 [ValidateAntiForgeryTokenAttribute](/previous-versions/aspnet/web-frameworks/dd492108(v=vs.118)) 및 허용 되는 HTTP 동사를 지정 하는 속성 ([AcceptVerbsAttribute](/previous-versions/aspnet/web-frameworks/dd470553%28v%3dvs.118%29) 를 [HttpPostAttribute](/previous-versions/aspnet/web-frameworks/ee264023%28v%3dvs.118%29)하십시오 [HttpPutAttribute](/previous-versions/aspnet/web-frameworks/ee470909%28v%3dvs.118%29), 또는 [HttpDeleteAttribute](/previous-versions/aspnet/web-frameworks/ee470917%28v%3dvs.118%29)). 또한를 호출 해야 합니다 [HtmlHelper.AntiForgeryToken()](/previous-versions/aspnet/web-frameworks/dd504812%28v%3dvs.118%29) MVC 뷰 또는 Razor 웹 페이지 메서드. 예를 들어 참조 [edit 메서드를 검사 하 고 뷰 편집](/aspnet/mvc/overview/getting-started/introduction/examining-the-edit-methods-and-edit-view)합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

하는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다.

- ASP.NET MVC 컨트롤러 작업에 해로운 파생 작업이 없습니다.

- 응용 프로그램을 다른 방식으로 위조 방지 토큰을 확인합니다.

## <a name="validateantiforgerytoken-attribute-example"></a>ValidateAntiForgeryToken 특성 예제

### <a name="violation"></a>위반

```csharp
namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        public ActionResult TransferMoney(string toAccount, string amount)
        {
            // You don't want an attacker to specify to who and how much money to transfer.

            return null;
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
using System;
using System.Xml;

namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        [HttpPost]
        [ValidateAntiForgeryToken]
        public ActionResult TransferMoney(string toAccount, string amount)
        {
            return null;
        }
    }
}
```

## <a name="httpget-attribute-example"></a>HttpGet 특성 예제

### <a name="violation"></a>위반

```csharp
namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        public ActionResult Help(int topicId)
        {
            // This Help method is an example of a read-only operation with no harmful side effects.
            return null;
        }
    }
}
```

### <a name="solution"></a>솔루션

```csharp
namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        [HttpGet]
        public ActionResult Help(int topicId)
        {
            return null;
        }
    }
}
```
