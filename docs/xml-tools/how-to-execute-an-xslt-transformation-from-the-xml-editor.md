---
title: '방법: XML 편집기에서 XSLT 변형 실행'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 56a0fe82-5231-487d-8b6e-a08a9b04e0fc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 74432b7807f901253646f28a3e1bf4664f673326
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-execute-an-xslt-transformation-from-the-xml-editor"></a>방법: XML 편집기에서 XSLT 변형 실행

XML 편집기에서 XSLT 스타일시트를 XML 문서에 연결하고 변형을 수행하며 출력을 볼 수 있습니다. XSLT 변형의 결과로 나타나는 출력이 새 문서 창에 표시됩니다.

**출력** 속성에 대 한 출력 파일 이름을 지정 합니다. 경우는 **출력** 속성이 비어 있으면 임시 디렉터리에는 파일 이름이 생성 됩니다. 파일 확장명은 스타일시트에 있는 `xsl:output` 요소를 기반으로 하며 .xml, .txt 또는 .htm일 수 있습니다.

경우는 **출력** 속성.htm와 파일 이름을 지정 또는.html 확장명, XSLT 출력을 사용 하 여 미리 보기 [!INCLUDE[msCoName](../xml-tools/includes/msconame_md.md)] Internet Explorer 합니다. 다른 모든 파일 확장명은 [!INCLUDE[msCoName](../xml-tools/includes/msconame_md.md)] Visual Studio에서 선택한 기본 편집기를 사용하여 열립니다. 예를 들어, 파일 확장명이 .xml인 경우 Visual Studio에서는 XML 편집기를 사용합니다.

## <a name="to-execute-an-xslt-transformation-from-an-xml-document"></a>XML 문서에서 XSLT 변환을 실행하려면

1.  XML 편집기에서 XML 문서를 엽니다.

2.  XSLT 스타일시트를 XML 문서에 연결합니다.

    -   XML 문서에 `xml-stylesheet` 처리 명령을 추가합니다. 예를 들어, 문서 프롤로그에 다음 `<?xml-stylesheet type='text/xsl' href='filename.xsl'?>` 줄을 추가합니다.

         -또는-

    -   추가 하 여 XSLT 스타일 시트는 **속성** 창. 문서에서 **속성 창**, 클릭는 **찾아보기** 에 대 한 단추는 **스타일 시트** 필드, XSLT 스타일 시트를 선택 하 고, 클릭 **열**.

3.  클릭는 **ShowXSL 출력** 단추는 **XML 편집기** 도구 모음입니다.

    > [!NOTE]
    > XML 문서에 연결된 스타일시트가 없을 경우 대화 상자에서 사용할 스타일시트를 지정하라는 메시지가 나타납니다.
    >
    >  XSLT 변환의 결과로 나타나는 출력이 새 문서 창에 표시됩니다.

## <a name="to-execute-an-xslt-transformation-from-an-xslt-style-sheet"></a>XSLT 스타일시트에서 XSLT 변환을 실행하려면

1.  XML 편집기에서 XSLT 스타일시트를 엽니다.

2.  XML 문서를 지정 된 **입력** 문서의 필드 **속성** 창.

    > [!NOTE]
    > XML 문서는 변형에 사용되는 입력 문서입니다. XSLT 변형을 시작할 때 문서가 지정 되지 않은 경우는 **파일 열기** 대화 상자가 나타나고 해당 시간에 문서를 지정할 수 있습니다.

3.  클릭는 **ShowXSLT 출력** 단추는 **XML 편집기** 도구 모음입니다.

     XSLT 변형의 결과로 나타나는 출력이 새 문서 창에 표시됩니다.

## <a name="to-provide-a-different-output-file-name"></a>다른 출력 파일 이름을 지정하려면

1.  파일 이름을 지정는 **출력** 문서의 필드 **속성** 창.

2.  클릭는 **ShowXSLT 출력** 단추는 **XML 편집기** 도구 모음입니다.

     XSLT 변형의 결과로 나타나는 출력이 새 문서 창에 표시 되 고 출력 창에 사용 되는 편집기의 파일 확장명에 따라 달라 집니다 프로그램 **출력** 문서 속성입니다.

## <a name="see-also"></a>참고 항목

- [XML 편집기](../xml-tools/xml-editor.md)