---
title: '방법: 사용할 XML 스키마 선택'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: d6fda3ef-d465-4788-8514-2f2d528d658c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d835a8592108b549a109f7bb7e128a8ae5b01611
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2018
---
# <a name="how-to-select-the-xml-schemas-to-use"></a>방법: 사용할 XML 스키마를 선택 합니다.

XML 편집기에 있는 스키마 캐시 제공에서 *%InstallDir%\Xml\Schemas* 디렉터리입니다. 이 스키마 캐시에는 잘 알려진 XML 스키마가 포함되어 있으며 이 스키마는 IntelliSense 및 XML 문서 유효성 검사에 사용됩니다.

**스키마** 문서 속성은 하나 이상의 XML 스키마 정의 언어 (XSD) 스키마를 사용 하 여 선택 하는 데 사용 합니다. 즉, 이 속성을 사용하면 스키마 캐시에서 스키마를 선택하거나 캐시에 없는 스키마를 지정할 수 있습니다.

지정한 스키마의 숨겨진된 솔루션 사용자 옵션 파일에 저장 됩니다 (. *suo*), 다른 모든 XML 함께 문서 속성입니다. 그러므로 다음 번에 솔루션을 열 때 이러한 값을 다시 입력하지 않아도 됩니다.

> [!NOTE]
> 편집기에서는 인라인 스키마 또는 `xsd:schemaLocation` 특성이 참조하는 스키마를 사용하여 유효성을 검사할 수 있습니다. 자세한 내용은 참조 [XML 문서 유효성 검사](../xml-tools/xml-document-validation.md)합니다.

## <a name="to-select-an-xml-schema-from-the-schema-cache"></a>스키마 캐시에서 XML 스키마를 선택 하려면

1.  XML 편집기에서 파일을 엽니다.

2.  문서 속성 창에서 단추를 클릭는 **스키마** 필드입니다.

     **XML 스키마** 대화 상자가 표시 됩니다. 대화 상자에 나열 된 모든 스키마는 합니다. *xsd* 스키마 캐시에서 확장명이 (스키마에서 참조를 포함 하는 *catalog.xml* 파일), 및 Visual Studio에서 열려 있는 현재 솔루션에서 참조 되는 모든 스키마도는 `xsd:schemaLocation` 특성 또는에서 참조 되는 **스키마** 속성입니다.

3.  다음 중 하나를 수행하여 유효성 검사에 사용할 스키마를 선택합니다.

    -   에 나열 된 스키마를 선택는 **XML 스키마** 대화 상자에서 클릭 된 **사용** 열을 선택한 후 **이 스키마를 사용 하 여**합니다.

     -또는-

    -   에 나열 된 여러 스키마를 선택는 **XML 스키마** 대화 마우스 단추를 선택 **이 스키마를 사용 하 여**합니다.

4.  **확인**을 클릭합니다.

     선택한 스키마 목록에 다시 복사 되 고 **스키마** 문서 속성입니다.

## <a name="to-add-an-xml-schema-to-the-schema-cache"></a>스키마 캐시에 XML 스키마를 추가 하려면

1.  문서 속성 창에서 단추를 클릭는 **스키마** 필드입니다.

2.  **추가**를 클릭합니다.

     열립니다는 **XSD 스키마 열기** 대화 상자.

3.  스키마 캐시에 추가할 스키마를 찾아 선택합니다.

4.  클릭 **열려**합니다.

     스키마에 추가 스키마 캐시 하 고이 **사용** 열 값으로 설정 됩니다 **이 스키마를 사용 하 여**합니다.

## <a name="to-delete-an-xml-schema-from-the-schema-cache"></a>스키마 캐시에서 XML 스키마를 삭제 하려면

1.  문서 속성 창에서 단추를 클릭는 **스키마** 필드입니다.

2.  스키마를 제거 하 고 클릭 한 다음 선택 **제거**합니다.

     그러면 스키마가 메모리 내 스키마 캐시에서 제거되지만 파일 시스템에서는 제거되지 않습니다.

    > [!NOTE]
    > 통해 스키마에 대 한 참조가 아직 남아 있으면는 `schemaLocation` 특성 또는 일치 하는 `targetNamespace` 다음 **제거** 자동 연결으로 인해 이러한 상황에서 작동 하지 것입니다. 이 경우에 것으로 스키마를 표시 하는 **선택한 스키마를 사용 하지 않는** 에 **사용** 열입니다.

## <a name="see-also"></a>참고자료

- [스키마 캐시](../xml-tools/schema-cache.md)
- [XML 스키마 대화 상자](../xml-tools/xml-schemas-dialog-box.md)
- [XML 편집기](../xml-tools/xml-editor.md)