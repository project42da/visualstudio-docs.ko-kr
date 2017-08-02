---
title: "이동 | Microsoft 문서"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 509b2107-23d1-4fb3-987f-ab99ef45b72e
author: BrianPeek
ms.author: brpeek
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 3b812629bf0f655f39c35a56eb1b3ca9113303a6
ms.openlocfilehash: 8bf6d49b21d128d15f5312fb230d4a8e7a8195af
ms.lasthandoff: 03/01/2017

---

# <a name="go-to"></a>이동
키보드와 마우스를 통해 Visual Studio IDE 내에서 코드를 쉽게 탐색하는 여러 가지 방법이 있습니다.

<!-- VERSIONLESS -->
## <a name="go-to-all"></a>전체로 이동
이 기능은 Visual Studio 2017 이상에 있습니다.  코드를 탐색하여 찾으려는 특정 비트를 찾을 수 있습니다.  간단한 통합 인터페이스에서 특정 줄, 형식, 기호, 파일 등을 검색할 수 있습니다.

### <a name="how-to-use"></a>사용 방법
* **키보드**
  * **Ctrl+,** 또는 **Ctrl+T**를 누릅니다.  바로 가기 키는 선택한 프로필에 따라 다를 수 있습니다.
* **마우스**
  * **편집 > 이동 > 전체로 이동**을 선택합니다.

이렇게 하면 기본적으로 IDE의 오른쪽 위에 작은 창이 표시됩니다.

![전체로 이동](~/docs/ide/media/gotoall.png)

여기서 진행하는 방법에는 여러 가지가 있습니다.
* 접두사 없이 텍스트를 입력하여 텍스트 상자 아래에서 선택한 [필터 아이콘](#filtered-searches)을 사용해서 검색합니다.
* [접두사](#filtered-searches) 뒤에 검색할 텍스트를 입력합니다.
* 물음표(?)를 입력하여 추가 도움말을 확인합니다.
  ![전체로 이동 도움말](~/docs/ide/media/gotoall_help.png)

### <a name="filtered-searches"></a>필터링된 검색
검색 범위를 특정 형식으로 좁히려면 입력 시 접두사를 사용하거나, 아래와 같이 검색 창 아래에 표시되는 아이콘을 사용합니다.

접두사 | 아이콘 | 바로 가기 | 설명
:----: | ---- | -------- | ---
#      | ![기호 아이콘](~/docs/ide/media/gotoall_symbolicon.png) | Ctrl+1, Ctrl+S | 일치하는 기호를 찾습니다.
f      | ![파일 아이콘](~/docs/ide/media/gotoall_fileicon.png)     | Ctrl+1, Ctrl+F | 일치하는 파일 이름을 찾습니다.
분      | ![멤버 아이콘](~/docs/ide/media/gotoall_membericon.png) | Ctrl+1, Ctrl+M | 일치하는 멤버를 찾습니다.
t      | ![형식 아이콘](~/docs/ide/media/gotoall_typeicon.png)     | Ctrl+1, Ctrl+T | 일치하는 형식을 찾습니다.
:      | ![줄 아이콘](~/docs/ide/media/gotoall_lineicon.png)     | Ctrl+G         | 입력한 줄 번호로 이동합니다.

### <a name="search-locations"></a>검색 위치
검색 범위를 특정 위치로 좁히려면 두 개의 문서 아이콘을 사용합니다.

아이콘 | 설명
---- | ---
![현재 문서](~/docs/ide/media/gotoall_currentdocument.png) | 현재 문서에서만 검색합니다.
![외부 문서](~/docs/ide/media/gotoall_external.png) | 프로젝트/솔루션에 있는 문서와 외부 문서를 검색합니다.

### <a name="settings"></a>설정
오른쪽 아래에 있는 기어 아이콘 ![기어 아이콘](~/docs/ide/media/gotoall_gear.png) 을 클릭하면 이 기능의 작동 방식을 변경할 수 있습니다.

설정 | 설명
------- | ---
미리 보기 탭 사용 | 선택한 항목을 IDE의 미리 보기 탭에서 즉시 표시합니다.
자세한 정보 표시    | 문서 주석의 프로젝트, 파일, 줄 및 요약 정보를 창에 표시합니다.
창 가운데 맞춤   | 이 창을 오른쪽 위가 아니라 IDE 가운데로 이동합니다.
<!-- END VERSIONLESS -->

## <a name="go-to-definition"></a>정의로 이동
형식의 소스로 이동하고 새 탭에서 결과를 엽니다.

입력        | 함수 
------------ | ---
**키보드** | 형식 이름 내부에 텍스트 커서를 놓고 **F12** 키를 누릅니다.
**마우스**    | 형식 이름을 마우스 오른쪽 단추로 클릭하고 **정의로 이동**을 선택합니다.

## <a name="peek-definition"></a>정의 피킹
새 탭이 아니라 팝업 창에서 형식 정의를 미리 봅니다.

입력        | 함수 
------------ | ---
**키보드** | 형식 이름 내부에 텍스트 커서를 놓고 **Alt+F12**를 누릅니다.
**마우스**    | 형식 이름을 마우스 오른쪽 단추로 클릭하고 **정의 피킹(Peeking)**을 선택합니다.

팝업 창에서 다른 정의를 피킹하는 경우 팝업 위에 표시되는 원과 화살표를 사용하여 탐색할 수 있는 이동 경로가 시작됩니다.  자세한 내용은 [방법: 정의 피킹(Peeking)을 사용하여 코드 보기 및 편집(Alt+F12)](how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md)을 참조하세요.

## <a name="go-to-implementation"></a>구현으로 이동
기본 클래스 또는 형식에서 해당 구현으로 이동합니다.  여러 구현이 있는 경우 **기호 찾기 결과** 창에 표시됩니다.

입력        | 함수 
------------ | ---
**키보드** | 형식 이름 내부에 텍스트 커서를 놓고 **Ctrl+F12**를 누릅니다.
**마우스**    | 형식 이름을 마우스 오른쪽 단추로 클릭하고 **구현으로 이동**을 선택합니다.

## <a name="find-all-references"></a>모든 참조 찾기
메서드/속성/변수가 사용되는 모든 위치를 찾습니다.  이 옵션을 사용하여 데드 코드를 확인하고 큰 리팩터링의 가능한 부작용을 검사할 수 있습니다.  결과 간에 이동하려면 **F8** 키를 누릅니다.

입력        | 함수 
------------ | ---
**키보드** | 형식 이름 내부에 텍스트 커서를 놓고 **Ctrl+K, R**을 누릅니다.
**마우스**    | 형식 이름을 마우스 오른쪽 단추로 클릭하고 **모든 참조 찾기**를 선택합니다.

## <a name="navigating-results"></a>결과 탐색
Visual Studio의 탐색 기능을 사용하는 경우 스택에서 앞뒤로 탐색할 수 있습니다.

입력        | 함수 
------------ | ---
**Ctrl+-**          | 스택에서 뒤로 탐색합니다.
**Ctrl+Shift+-**    | 스택에서 앞으로 탐색합니다.

**보기 > 뒤로 탐색** 및 **보기 > 앞으로 탐색** 메뉴 항목을 사용할 수도 있습니다.
