---
title: "방법: XML 파일의 편집 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07fa3ecf-6345-4d30-9d85-d5ef5b083319
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8720fe94797e212cb332368572b291ce7fb40a26
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-edit-xml-files"></a>방법: XML 파일 편집
XML 편집기는 XML 파일을 위한 새 편집기입니다. 이 편집기는 독립 실행형 XML 파일 또는 Visual Studio 프로젝트에 연결된 파일에 사용할 수 있습니다. XML 편집기는 .config, .dtd, .xml, .xsd, .xdr, .xsl, .xslt 및 .vssettings 파일 확장명과 연결됩니다. 또한 특정 편집기가 등록되지 않은 파일 형식과 XML 또는 DTD 내용이 포함된 파일 형식과도 연결되어 있습니다.  
  
> [!NOTE]
>  XHTML 문서는 HTML 편집기에서 처리됩니다.  
  
### <a name="to-edit-an-xml-file"></a>XML 파일을 편집하려면  
  
1.  편집할 파일을 두 번 클릭합니다.  
  
### <a name="to-add-a-new-xml-file-to-a-project"></a>새 XML 파일을 프로젝트에 추가하려면  
  
1.  **프로젝트** 메뉴 선택 **새 항목 추가**합니다.  
  
2.  선택 **XML 파일** 에서 **템플릿** 창.  
  
3.  에 파일 이름을 입력 된 **이름** 필드 및 키를 눌러 **추가**합니다.  
  
     XML 파일이 프로젝트에 추가되고 XML 편집기에서 열립니다. 파일에는 기본 XML 선언, `<?xml version="1.0" encoding="utf-8" ?>`이 포함됩니다.  
  
### <a name="to-add-an-existing-xml-file-to-a-project"></a>기존 XML 파일을 프로젝트에 추가하려면  
  
1.  **프로젝트** 메뉴 선택 **기존 항목 추가**합니다.  
  
     **기존 항목 추가** 대화 상자가 나타납니다.  
  
2.  XML 파일 및 키를 눌러 선택 **추가**합니다.  
  
### <a name="to-create-a-new-xml-or-xslt-file"></a>새 XML 또는 XSLT 파일을 만들려면  
  
1.  **파일** 메뉴 선택 **새로**합니다.  
  
     **새 파일** 대화 상자가 나타납니다.  
  
2.  선택 **XML 파일** 새 XML 파일을; 만들거나 선택 **XSLT 파일** 새 XSLT 스타일 시트를 만들려고 합니다.  
  
3.  클릭 **열려**합니다.  
  
### <a name="to-create-a-project-for-xml-files"></a>XML 파일에 대한 프로젝트를 만들려면  
  
1.  **파일** 메뉴 선택 **새로**를 선택한 후 **프로젝트**합니다.  
  
     **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  사용자가 선택한 선택의 코드 언어를 선택 **빈 프로젝트**를 클릭 하 고 **확인**합니다.  
  
3.  프로젝트에 XML 파일을 추가합니다.  
  
     XML 편집기에서는 이 프로젝트에 추가한 스키마를 찾아서 이 프로젝트를 연 상태에서 편집하는 모든 XML, 스키마 또는 XSLT 파일의 유효성 검사 및 IntelliSense에 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 편집기](../xml-tools/xml-editor.md)   
 [XML 문서 속성, 속성 창](../xml-tools/xml-document-properties-properties-window.md)   
 [방법: XML 문서에서 XML 스키마 만들기](../xml-tools/how-to-create-an-xml-schema-from-an-xml-document.md)