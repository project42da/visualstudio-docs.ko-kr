---
title: Visual Studio의 XML 도구
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
f1_keywords:
- vb.xmldesigner
helpviewer_keywords:
- XML [Visual Studio], resources
- Enterprise Templates, XML and
- discovery files, XML
- server controls, XML and
- Web server controls, XML
- XSL
- XML [Visual Studio], data sources
- XML schemas
- XML [Visual Studio], SGML relationship to
- CSS, style sheets for XML
- XML [Visual Studio], .NET Framework classes
- data [Visual Studio], XML
- classes [Visual Studio], XML
- style sheets, for XML
- Web services
- SGML, XML
- XML [Visual Studio]
- datasets [Visual Basic], XML Schemas
- XSD schemas
- XSL, style sheets
- XMLDataDocument class
ms.assetid: 1fd5de47-2d61-4180-9539-c2c4bf9ab768
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 446378df2d73f4d0c2bb8eac45075fa51365cd6d
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693736"
---
# <a name="xml-tools-in-visual-studio"></a>Visual Studio의 XML 도구

*Extensible Markup Language (XML)* 는 데이터를 설명 하는 형식을 제공 하는 태그 언어입니다. 이 언어를 사용하면 콘텐츠를 보다 정확하게 선언하고 여러 플랫폼 간에 보다 의미 있는 검색 결과를 얻을 수 있습니다. 또한 XML을 사용하는 경우 표시를 데이터 자체와 구분할 수 있습니다. 예를 들어 HTML에서는 태그를 사용하여 데이터를 굵게, 기울임꼴 등으로 표시하도록 브라우저에 명령하지만 XML에서는 태그를 사용하여 구/군/시 이름, 기온, 기압 등의 데이터만을 설명합니다. XML을 사용 하 여 스타일 시트와 같은 언어 XSL (Extensible Stylesheet) 및 css 스타일 시트 () 브라우저에 데이터를 표시 합니다. XML에서는 데이터가 표시 및 프로세스와 구분되므로 여러 스타일시트 및 응용 프로그램을 적용하여 데이터를 원하는 방식으로 표시 및 처리할 수 있습니다.

XML은 웹을 통해 제공하도록 최적화된 SGML의 하위 집합으로, W3C(World Wide Web Consortium)에 의해 정의되었습니다. 이러한 표준화로 인해 구조화 된 데이터는 균일 하 고 응용 프로그램이 나 공급 업체와 무관 합니다.

XML은 Visual Studio 및.NET Framework의 여러 기능의 핵심입니다. 다음 문서는 Visual Studio 및.NET Framework에서 제공 되는 XML 관련 기능 및 도구의 이름을 지정 합니다.

자세한 내용은 참조는 <xref:System.Xml?displayProperty=fullName> 설명서입니다.

## <a name="reference"></a>참조

[Microsoft.VisualStudio.XmlEditor](http://go.microsoft.com/fwlink/?LinkID=165699) 노출 된 [XML 편집기](http://go.microsoft.com/fwlink/?LinkId=228249) 구문 분석 트리를 통해 [System.Xml.Linq](http://go.microsoft.com/fwlink/?LinkId=228250) 모든 XML 문서에 대 한 합니다.

[XML 표준 참조](http://msdn.microsoft.com/79c78508-c9d0-423a-a00f-672e855de401) XML, 문서 형식 정의 (DTD), XML 스키마 정의 언어 (XSD) 및 XSLT를 포함 하 여 XML 기술에 대 한 정보를 제공 합니다.

<xref:System.Xml?displayProperty=fullName> 클래스 및 구성 하는 다른 요소에 설명 된 <xref:System.Xml> 네임 스페이스 및 각 항목에 대해 보다 자세한 정보에 대 한 링크를 제공 합니다.

<xref:System.Xml.Serialization?displayProperty=fullName> 클래스 및 구성 하는 다른 요소에 설명 된 <xref:System.Xml.Serialization> 네임 스페이스 및 각 항목에 대 한 자세한 정보에 대 한 링크를 제공 합니다.

## <a name="related-sections"></a>관련 단원

[XML 문서 개체 모델 (DOM)](/dotnet/standard/data/xml/xml-document-object-model-dom) 설명 방법을 <xref:System.Xml.XmlDocument> 관련된 클래스가 W3C 문서 개체 모델 (Core) 수준 1 및 수준 2 네임 스페이스 지원 사양을 준수 합니다.

[XmlReader 및 XmlWriter를 사용 하 여 XML 데이터 처리](https://msdn.microsoft.com/library/cc189001(v=vs.95).aspx)

[XSLT 변환을](/dotnet/standard/data/xml/xslt-transformations) 설명 방법을 <xref:System.Xml.Xsl.XslCompiledTransform> 클래스는 XSLT 1.0 권장 사항 구현 합니다.

[XPath 데이터 모델을 사용 하 여 XML 데이터 처리](/dotnet/standard/data/xml/process-xml-data-using-the-xpath-data-model) 하는 방법을 설명 방법을 <xref:System.Xml.XPath.XPathNavigator> 클래스에 저장 된 XML 데이터를 처리할 수는 <xref:System.Xml.XPath.XPathDocument> 또는 <xref:System.Xml.XmlDocument> 개체입니다. <xref:System.Xml.XPath.XPathNavigator> 클래스는 XQuery 1.0 및 XPath 2.0 데이터 모델을 기반으로 하며 XML 데이터를 탐색 및 편집하는 데 사용할 수 있습니다.

[XML 개체 모델 SOM (스키마)](/dotnet/standard/data/xml/xml-schema-object-model-som) 만들고 제공 하 여 XML 스키마를 조작 하기 위해 사용 되는 클래스에 설명 된 <xref:System.Xml.Schema.XmlSchema> 클래스를 로드 및 스키마를 편집 합니다.