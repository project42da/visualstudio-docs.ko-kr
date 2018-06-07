---
title: 기타, XML, 텍스트 편집기, 옵션 대화 상자
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: reference
ms.assetid: fd3fff31-cddc-422d-a2f0-a5a1ef492afd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bd6ee70f99f3b82505d210ab95f8359b5c7f90c8
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34571772"
---
# <a name="miscellaneous-xml-text-editor-options-dialog-box"></a>기타, XML, 텍스트 편집기, 옵션 대화 상자

이 대화 상자에서는 XML 편집기에 대한 자동 완성 기능 및 스키마 설정을 변경할 수 있습니다. 에 액세스할 수 있습니다는 **옵션** 에서 대화 상자는 **도구** 메뉴.

> [!NOTE]
> 선택 하면 이러한 설정을 사용할 수 있습니다는 **텍스트 편집기** 폴더는 **XML** 폴더를 차례로 **기타** 옵션에서 **옵션** 대화 상자.


## <a name="auto-insert"></a>자동 삽입
 **닫기 태그**

 자동 완성 설정을 선택한 경우 사용자가 오른쪽 꺾쇠 괄호(>)를 입력하면 편집기에서 끝 태그를 자동으로 추가하여 시작 태그를 닫습니다(태그가 아직 닫히지 않은 경우). 이것은 기본적인 동작입니다.

 빈 요소를 완성하는 작업은 자동 완성 설정의 영향을 받지 않습니다. 빈 요소는 언제든지 백슬래시(/)를 입력하여 자동 완성할 수 있습니다.

 **특성 따옴표**

 XML 특성을 만들 때 `=" "` 문자가 삽입되며 큰따옴표 안에 캐럿(^)이 입력됩니다.

 기본으로 선택됩니다.

 **네임스페이스 선언**

 편집기에서는 네임스페이스 선언이 필요한 위치에 항상 네임스페이스 선언이 자동으로 삽입됩니다.

 기본으로 선택됩니다.

 **기타 태그 (주석, CDATA)**

 주석, CDATA, DOCTYPE, 처리 명령 및 기타 태그가 자동으로 완성됩니다.

 기본으로 선택됩니다.

## <a name="network"></a>네트워크
 **Dtd 및 스키마 자동 다운로드**

 HTTP 위치에서 스키마 및 DTD(문서 종류 정의)가 자동으로 다운로드됩니다. 이 기능은 자동 프록시 서버 검색 기능을 설정한 상태로 System.Net을 사용합니다.

 기본으로 선택됩니다.

## <a name="outlining"></a>개요
 **개요 모드로 파일 열기**

 파일을 열 때 개요 기능을 활성화합니다.

 기본으로 선택됩니다.

## <a name="caching"></a>캐싱
 **스키마**

 스키마 캐시의 위치를 지정합니다. 찾아보기 단추 (**...** ) 열립니다는 **디렉터리 찾아보기** 현재 스키마 캐시 위치에 대화 상자. 다른 디렉터리를 선택 하거나 대화 상자에서 폴더를 선택할 수 있습니다 마우스 오른쪽 단추로 클릭 하 고 선택 **열려** 디렉터리에 기능을 확인 하십시오.

## <a name="see-also"></a>참고자료

- [XML 문서 속성, 속성 창](../xml-tools/xml-document-properties-properties-window.md)
- [XML 편집기 구성 요소](../xml-tools/xml-editor-components.md)