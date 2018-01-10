---
title: "연습: XML 편집기 기능을 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea8dc357-2e66-455a-aec2-7ccaccfc9adf
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f7460071cc45c8e4994ad0a72d5f26dcce40c853
ms.sourcegitcommit: 5f436413bbb1e8aa18231eb5af210e7595401aa6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2018
---
# <a name="walkthrough-using-xml-editor-features"></a>연습: XML 편집기 기능 사용
이 연습 단계에서는 새 XML 문서를 만드는 방법을 보여 줍니다. 또한 이 연습에서는 XML 작성에 유용한 몇 가지 XML 편집기 기능을 사용합니다.  
  
> [!NOTE]
>  연습을 시작하기 전에 이 항목에서 아래에 포함된 hireDate.xsd 파일을 로컬 컴퓨터에 저장해야 합니다.  
  
### <a name="to-create-a-new-xml-file-and-associate-it-with-an-xml-schema"></a>새 XML 파일을 만들어 XML 스키마와 연결하려면  
  
1.  에 **파일** 메뉴에서 **새로**를 클릭 하 고 **파일**합니다.  
  
2.  선택 **XML 파일** 에 **템플릿** 창을 **열려**합니다.  
  
     편집기에서 새 파일이 열립니다. 파일에는 기본 XML 선언, `<?xml version="1.0" encoding="utf-8">`이 포함됩니다.  
  
3.  문서 속성 창에서 찾아보기 단추를 클릭 합니다. (**...** )에 **스키마** 필드입니다.  
  
     **XSD 스키마** 대화 상자가 표시 됩니다.  
  
4.  **추가**를 클릭합니다.  
  
     **XSD 스키마 열기** 대화 상자가 표시 됩니다.  
  
5.  HireDate.xsd 파일을 선택 하 고 클릭 **열려**합니다.  
  
6.  **확인**을 클릭합니다.  
  
     이제 XML 스키마가 XML 문서와 연결되었습니다. XML 스키마는 문서의 유효성을 검사하는 데 사용합니다. IntelliSense에서 유효한 요소의 멤버 목록을 채우는 데도 사용합니다.  
  
### <a name="to-add-data"></a>데이터를 추가하려면  
  
1.  편집기 창에 `<`를 입력합니다.  
  
     멤버 목록에 가능한 항목이 표시됩니다.  
  
    -   **!-** 메모를 추가 하려면.  
  
    -   **! DOCTYPE** 문서 형식을 추가할 수 있습니다.  
  
    -   **?** 처리 명령을 추가 합니다.  
  
    -   **직원** 루트 요소를 추가 합니다.  
  
2.  선택 **<!-** 하 주석 노드를 추가 하 고 ENTER 키를 누릅니다.  
  
     주석 끝 태그가 삽입되고 주석 시작 태그와 주석 끝 태그 사이에 커서가 놓입니다.  
  
3.  에 입력 **XML 파일 테스트**합니다.  
  
4.  새 줄에 입력 `<`를 선택 하 고 **직원** 멤버 목록에서 합니다.  
  
     XML 요소 `<employee`의 시작 부분이 추가됩니다. 이때 요소에 특성을 추가하거나 `>`를 입력하여 시작 태그를 닫을 수 있습니다.  
  
5.  `>`를 입력하여 태그를 닫습니다.  
  
6.  끝 태그가 추가됩니다. 끝 태그는 유효성 검사 오류를 나타내는 물결 무늬 밑줄과 함께 추가됩니다. 도구 설명에 다음 메시지가 표시됩니다. "'employee' 요소의 콘텐츠가 완전하지 않습니다. 'ID'가 있어야 합니다."  
  
7.  형식 `<` 선택 **ID** 멤버 목록에서 합니다. 그런 다음 `>`를 입력합니다.  
  
     XML 요소 `<ID></ID>`가 추가되고 ID 시작 태그 뒤에 커서가 놓입니다.  
  
8.  형식 **abc**합니다.  
  
     **abc** 물결선이 표시에 대 한 텍스트입니다. 도구 설명에 다음 메시지가 표시됩니다. "'ID' 요소 값의 데이터 형식이 잘못되었습니다."  
  
9. ID 요소를 마우스 오른쪽 단추로 클릭 하 고 선택 **정의로 이동**합니다.  
  
     새 문서 창에 hireDate.xsd 파일이 열리고 ID 스키마 요소 정의에 커서가 놓입니다.  
  
10. XML 파일을 반환 하 고 대체 된 **abc** 으로 텍스트 **123**합니다.  
  
     ID 요소 값에서 물결 무늬 밑줄과 도구 설명이 지워집니다. 직원 끝 태그에 대한 도구 설명에 다음 메시지가 표시됩니다. "'employee' 요소의 콘텐츠가 완전하지 않습니다. 'hire-date'가 있어야 합니다."  
  
11. ID 끝 태그 뒤에 커서를 놓고 `<`를 입력한 다음 멤버 목록에서 hire-date를 선택하고 `>`를 입력합니다.  
  
     XML 요소 `<hire-date></hire-date>`가 추가되고 hire-date 시작 태그 뒤에 커서가 놓입니다.  
  
12. 에 입력 **2003-01-10** 고용 날짜 값에 대 한 합니다.  
  
### <a name="to-format-the-xml-document"></a>XML 문서 서식을 지정하려면  
  
- 선택 된 **문서 서식** XML 편집기 도구 모음에서 단추입니다.
  
    XML 문서 서식이 다시 지정됩니다.  
  
### <a name="to-save-the-xml-document"></a>XML 문서를 저장하려면  
  
1.  **파일** 메뉴 선택 **다른 이름으로 저장**합니다.  
  
     **이름으로 파일 저장** 대화 상자가 표시 됩니다. 기본 파일 이름은 'XMLFile1'입니다.  
  
2.  파일 이름 및 XML 문서에 대 한 위치를 입력 하 고 클릭 **저장**합니다.  
  
## <a name="hiredatexsd-file"></a>hireDate.xsd 파일  
 다음 스키마 파일은 연습에 사용됩니다.  
  
```xml
<?xml version="1.0"?>  
<xs:schema attributeFormDefault="unqualified"  
     elementFormDefault="qualified" targetNamespace="urn:empl-hire"  
     xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="employee">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="ID" type="xs:unsignedShort" />  
        <xs:element name="hire-date" type="xs:date" />  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```
  
## <a name="see-also"></a>참고 항목  
 [XML 편집기](../xml-tools/xml-editor.md)