---
title: XML 문서 속성, 속성 창
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: reference
ms.assetid: 9dbb34d9-02ea-4201-b445-c98a0eb0d6db
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e7c29a6e106381e23007f8cb3d899cb3b3c0e387
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693567"
---
# <a name="xml-document-properties-properties-window"></a>XML 문서 속성, 속성 창

**속성** 창 XML 편집기에서 활성화 되어 있는 문서에 대 한 기본 정보를 제공 합니다. 현재 활성화되어 있는 XML 문서의 형식에 따라 사용할 수 있는 속성이 달라집니다.

> [!NOTE]
> 모든 XML 문서 속성은 솔루션에 저장됩니다. 그러면 다음에 솔루션을 열 때는 이러한 값을 다시 입력하지 않아도 됩니다.

 **인코딩**

 파일에 대한 문자 인코딩입니다. 이 속성을 변경하면 XML 선언의 인코딩 특성도 변경되며 XML 선언의 인코딩 특성을 변경하면 이 속성도 변경됩니다. 파일을 저장할 때 새 인코딩을 사용하여 파일이 인코딩됩니다.

 **입력**

 XSLT 스타일시트에 연결된 입력 문서입니다. 사용 되는 **ShowXSLT 출력** 명령입니다. 찾아보기 사용 하 여 문서를 선택할 수 있습니다 (**...** ) 단추입니다.

 편집기 창에서 XSLT 파일이 현재 활성화되어 있는 경우에만 이 속성이 표시됩니다.

 **출력**

 XML 문서를 변형할 때 생성되는 파일입니다.

 파일을 지정하지 않으면 파일 확장명을 결정하는 `method` 요소의 `xsl:output` 특성을 기준으로 기본 파일 이름이 생성됩니다. 기본 파일은 현재 사용자의 임시 디렉터리에 있습니다.

 **스키마**

 유효성 검사에 사용할 스키마입니다. 이 단추를 클릭는 **XSD 스키마** 사용할 스키마를 선택 하는 데 사용할 수 있는 대화 상자.

 스키마 경로를 입력할 수도 있습니다. 여러 스키마를 지정할 경우 각 스키마 경로를 큰따옴표로 묶어야 합니다.

 **스타일 시트**

 문서를 변환 하는 데 사용 되는 XSLT 파일 때는 **XSLT 출력 표시** 명령을 사용 합니다. 이 필드를 비워 두면는 **XSLT 출력 표시** 명령을 사용 하 여에 제공 된 값을 사용 하 여 편집기의 `xml-stylesheet` 처리 명령 또는 문서를 묻는 메시지를 파일 이름입니다.

 다른 스타일 시트 되어야 함을 지정 하려면이 속성을 사용할 수는 XSLT 파일을 편집할 때 때 사용 되는 **XSLT 출력 표시** 또는 **XSLT 디버깅** 명령을 선택 합니다. 예를 들어, 부모 스타일시트에 포함된 스타일시트를 편집할 때 이 작업을 수행할 수 있습니다.

## <a name="see-also"></a>참고자료

- [XML 편집기](../xml-tools/xml-editor.md)
- [XML 편집기 구성 요소](../xml-tools/xml-editor-components.md)