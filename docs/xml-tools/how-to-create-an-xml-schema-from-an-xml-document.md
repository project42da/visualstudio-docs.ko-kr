---
title: '방법: XML 문서에서 XML 스키마 만들기'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 1d6700a9-fd67-4794-8997-399589e99bec
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2f33fc5b48b9fd6b1cc08570e62e73f05fd19e70
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2018
---
# <a name="how-to-create-an-xml-schema-from-an-xml-document"></a>방법: XML 문서에서 XML 스키마 만들기

XML 편집기를 사용하여 XML 문서에서 XSD(XML 스키마 정의 언어) 스키마를 만들 수 있습니다. XML 인스턴스 문서는 다음 방법으로 스키마를 생성하는 방법을 결정합니다.

-   XML 문서에 연결된 스키마 또는 DTD(문서 형식 정의)가 없을 경우 XML 문서의 데이터를 사용하여 새 XML 스키마를 유추합니다.

-   XML 문서에 연결된 DTD가 있을 경우 외부 DTD 및 내부 하위 집합이 해당 XML 스키마로 변환됩니다.

-   XML 문서에 인라인 XDR(XML-Data Reduced) 스키마가 포함된 경우 XDR 스키마가 해당 XML 스키마로 변환됩니다.

그런 다음 생성된 스키마를 사용하여 XML 문서에 대해 IntelliSense를 제공합니다.

스키마 유추 엔진에 대 한 자세한 내용은 참조 [XML 스키마 유추](/dotnet/standard/data/xml/inferring-an-xml-schema)합니다.

## <a name="to-create-an-xml-schema"></a>XML 스키마를 만들려면

1.  XML 인스턴스 문서를 XML 편집기에 로드합니다.

2.  클릭는 **Create Schema** 에서 단추는 **도구 모음**합니다.

     XML 스키마 문서가 만들어지고 XML 인스턴스 문서에 있는 각 네임스페이스에 대해 열립니다. 각 스키마는 임시 기타 파일로 열립니다.

     스키마를 디스크에 저장하거나 프로젝트에 추가 또는 삭제할 수 있습니다.

    > [!NOTE]
    >  **Create Schema** 명령을 XML 편집기의 바로 가기 메뉴에서 사용할 수도 있습니다는 **XML** 메뉴.

## <a name="see-also"></a>참고자료

- [XML 편집기](../xml-tools/xml-editor.md)