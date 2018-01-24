---
title: "CA3076: 안전 하지 않은 XSLT 스크립트 실행 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 66d415b792558dce91de0205ee688fecb5caa182
ms.sourcegitcommit: 49aa031cbebdd9c7ec070c713afb1a97d1ecb701
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2018
---
# <a name="ca3076-insecure-xslt-script-execution"></a>CA3076: 안전하지 않은 XSLT 스크립트 실행

|||  
|-|-|  
|TypeName|InsecureXSLTScriptExecution|  
|CheckId|CA3076|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경 아님|  

## <a name="cause"></a>원인

.NET 응용 프로그램에서 비보안 방식으로 XSLT(Extensible Stylesheets Language Transformations)를 실행하는 경우 프로세서는 공격자에게 중요한 정보를 노출하여 서비스 거부 및 사이트 간 공격을 유발할 수 있는 신뢰할 수 없는 URI 참조를 확인할 수 있습니다. 자세한 내용은 참조 [XSLT 보안 Considerations(.NET Guide)](/dotnet/standard/data/xml/xslt-security-considerations)합니다.

## <a name="rule-description"></a>규칙 설명

**XSLT** 는 XML 데이터를 변환에 대 한 World Wide Web Consortium (W3C) 표준입니다. XSLT는 XML 데이터를 HTML, 고정 길이 텍스트, 쉼표로 구분된 텍스트 또는 기타 XML 형식 등으로 변환하기 위한 스타일시트를 작성하는 데 일반적으로 사용됩니다. 이 기능은 프로젝트에서 기본적으로는 금지되어 있지만 사용하도록 설정할 수 있습니다.

공격 영역을 노출하지 않도록 하기 위해 이 규칙은 XslCompiledTransform.<xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> 가 안전하지 않은 <xref:System.Xml.Xsl.XsltSettings> 및 <xref:System.Xml.XmlResolver>인스턴스가 함께 수신될 때마다 트리거되어 악성 스크립트를 처리합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

- 안전하지 않은 XsltSettings 인수를 XsltSettings.<xref:System.Xml.Xsl.XsltSettings.Default%2A> 또는 문서 함수 및 스크립트 실행을 사용하지 않도록 하는 인스턴스로 바꿉니다.

- <xref:System.Xml.XmlResolver> 인수를 null 또는 <xref:System.Xml.XmlSecureResolver> 인스턴스로 바꿉니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우

입력 출처를 신뢰할 수 있는지 확신할 수 없으면 이 경고의 규칙이 표시되지 않도록 설정하지 않도록 합니다.

## <a name="pseudo-code-examples"></a>의사 코드 예제

### <a name="violationmdashuses-xsltsettingstrustedxslt"></a>Violation&mdash;uses XsltSettings.TrustedXslt

```csharp
using System.Xml;  
using System.Xml.Xsl;  
  
namespace TestNamespace   
{   
    class TestClass   
    {  
         void TestMethod()
        {    
             XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
             var settings = XsltSettings.TrustedXslt;
             var resolver = new XmlUrlResolver();
             xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn   
        }  
    }
} 
```

### <a name="solutionmdashuse-xsltsettingsdefault"></a>Solution&mdash;use XsltSettings.Default

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
        void TestMethod()
        {
            XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
            var settings = XsltSettings.Default;
            var resolver = new XmlUrlResolver();
            xslCompiledTransform.Load("testStylesheet", settings, resolver);
        }
    }
}
```

### <a name="violationmdashdocument-function-and-script-execution-not-disabled"></a>위반&mdash;문서 함수 및 스크립트 실행을 사용 하지 않도록 설정

```csharp
using System.Xml;
using System.Xml.Xsl;
  
namespace TestNamespace   
{   
    class TestClass   
    {   
        private static void TestMethod(XsltSettings settings)
        {   
            try   
            {   
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
                var resolver = new XmlUrlResolver();
                xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn
            }
            catch { throw; }
            finally { }
        }
    }
}
```

### <a name="solutionmdashdisable-document-function-and-script-execution"></a>솔루션&mdash;문서 함수 및 스크립트 실행을 사용 하지 않도록 설정

```csharp
using System.Xml;
using System.Xml.Xsl;

namespace TestNamespace
{
    class TestClass
    {
        private static void TestMethod(XsltSettings settings)
        {
            try
            {
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();
                settings.EnableDocumentFunction = false;
                settings.EnableScript = false;
                var resolver = new XmlUrlResolver();
                xslCompiledTransform.Load("testStylesheet", settings, resolver);
            }
            catch { throw; }
            finally { }
        }
    }
}
```

## <a name="see-also"></a>참고 항목

[XSLT 보안 고려 사항 (.NET 가이드)](/dotnet/standard/data/xml/xslt-security-considerations)