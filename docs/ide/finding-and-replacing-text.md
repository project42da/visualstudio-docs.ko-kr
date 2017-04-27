---
title: "텍스트 찾기 및 바꾸기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.find"
  - "vs.findreplacecontrol"
  - "vs.findreplace.findsymbol"
  - "vs.findreplace.symbol"
  - "findresultswindow"
  - "vs.findreplace.quickreplace"
  - "vs.findsymbol"
  - "vs.findinfiles"
  - "vs.findresults1"
  - "vs,findsymbolwindow"
  - "vs.findreplace.quickfind"
  - "vs.lookin"
  - "vs.replace"
helpviewer_keywords: 
  - "find"
  - "찾기 및 바꾸기"
  - "파일에서 찾기 대화 상자"
  - "텍스트 찾기"
  - "find, 기호"
  - "find, 텍스트"
  - "replace"
  - "바꾸기 대화 상자"
  - "파일에서 바꾸기 대화 상자"
  - "텍스트 바꾸기"
  - "텍스트 검색"
  - "텍스트 검색, 텍스트 찾기 및 바꾸기"
  - "텍스트, 찾기 및 바꾸기"
ms.assetid: a62545c3-1570-4d12-99fb-a82607eb35a1
caps.latest.revision: 31
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 31
---
# 텍스트 찾기 및 바꾸기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 코드 편집기 및 **찾기 결과** 창과 같은 특정 텍스트 기반 출력 창\(**찾기 및 바꾸기** 컨트롤 또는 **파일에서 찾기\/바꾸기** 사용\)에서 텍스트를 찾고 바꿀 수 있습니다.  XAML 디자이너와 Windows Forms 디자이너 및 도구 창과 같은 일부 디자이너 창에서 검색하여 바꿀 수도 있습니다.  
  
 현재 문서, 현재 솔루션 또는 사용자 지정 폴더 집합에 대한 검색 범위를 지정할 수 있습니다.  또한 다중 파일 검색에 대한 일련의 파일 확장명을 지정할 수도 있습니다.  .NET 정규식을 사용하여 구문 검색을 사용자 지정할 수 있습니다.  
  
 정규식을 찾고 바꾸려면 [Visual Studio에서 정규식 사용](../ide/using-regular-expressions-in-visual-studio.md)을 참조하십시오.  
  
> [!TIP]
>  **찾기\/명령** 상자는 계속하여 도구 모음 컨트롤로 사용할 수 있지만 더 이상 기본값으로는 보이지는 않습니다.  **표준** 도구 모음에서 **단추 추가\/제거**를 선택한 다음 **찾기**를 선택하여 **찾기\/명령** 상자를 표시할 수 있습니다.  자세한 내용은 [찾기\/명령 상자](../ide/find-command-box.md)을 참조하십시오.  
  
## 찾기 및 바꾸기 컨트롤  
 **찾기 및 바꾸기** 컨트롤은 코드 편집기 창의 오른쪽 위 모퉁이에 나타납니다.  **찾기 및 바꾸기** 컨트롤은 현재 문서에서 지정된 검색 문자열이 발견될 때마다 즉시 강조 표시합니다.  검색 제어의 **다음 찾기** 단추 또는 **이전 찾기** 단추를 선택하여 항목 사이를 탐색할 수 있습니다.  
  
 **찾기** 텍스트 상자 옆에 있는 단추를 선택하여 대체 옵션에 액세스할 수 있습니다.  한 번에 하나씩 대체하려면 **바꾸기** 텍스트 상자 옆의 **다음 바꾸기** 단추를 선택합니다.  모든 일치 항목을 바꾸려면 **모두 바꾸기** 단추를 선택합니다.  
  
 일치하는 항목의 강조 색을 변경하려면 **도구** 메뉴에서 **옵션**을 선택한 다음 **환경**을 선택하고 **글꼴 및 색**을 선택합니다.  **설정 표시** 목록에서 **텍스트 편집기**를 선택한 다음 **표시 항목** 목록에서 **강조 표시\(확장명\) 찾기**를 선택합니다.  
  
### 도구 창 검색  
 **편집** 메뉴에서 **찾기 및 바꾸기**를 선택하여\(또는 Ctrl\+F\) **출력** 창, **찾기 결과** 창과 같은 텍스트 창 또는 코드에서 **찾기** 컨트롤을 사용할 수 있습니다.  
  
 찾기 컨트롤 버전은 일부 도구 창에서도 사용할 수 있습니다.  예를 들어 검색 상자에 텍스트를 입력하여 **도구상자** 창에서 제어 목록을 필터링할 수 있습니다.  콘텐츠를 검색할 수 있는 다른 도구 창은 **솔루션 탐색기**, **속성** 창 및 **팀 탐색기**를 포함합니다.  
  
## 파일에서 찾기\/바꾸기  
 검색 범위를 정의할 수 있는 점을 제외하고는 **파일에서 찾기\/바꾸기**는 **찾기 및 바꾸기** 제어와 같이 작동됩니다.  편집기에 현재 열려 있는 파일을 검색할 수 있을 뿐만 아니라 모든 열린 문서, 전체 솔루션, 현재 프로젝트 및 선택된 폴더 집합도 검색할 수 있습니다.  또한 파일 확장명으로 검색할 수도 있습니다.  **파일 열기\/파일에서 바꾸기** 대화 상자에 액세스하려면 **편집** 메뉴에서 **찾기 및 바꾸기**를 선택합니다\(또는 Ctrl\+Shift\+F\).  
  
 **모두 찾기**를 선택한 경우 **찾기 결과** 창이 열리고 검색 결과가 나열됩니다.  목록에서 결과를 선택하면 연관된 파일이 표시되고 일치하는 항목이 강조 표시됩니다.  편집 파일이 미리 열려 있지 않는 경우 탭 우측에 있는 미리 보기 탭에서 파일을 엽니다.  **찾기** 제어를 사용하여 **찾기 결과** 목록을 통해 검색할 수 있습니다.  
  
### 사용자 지정 검색 폴더 집합 만들기  
 **찾는 위치** 상자 옆의 **검색 폴더 선택** 단추\(**…**와 유사\)을 선택하여 검색 범위를 정의할 수 있습니다.  **검색 폴더 선택** 대화 상자에서 검색할 폴더 집합을 지정하고 나중에 다시 사용할 수 있도록 지정을 저장할 수 있습니다.  드라이브를 로컬 컴퓨터에 매핑한 경우에만 원격 컴퓨터의 폴더를 지정할 수 있습니다.  
  
### 사용자 지정 구성 요소 집합 만들기  
 **찾는 위치** 상자 옆의 **사용자 지정 구성 요소 집합 편집** 단추를 선택하여 구성 요소 집합을 검색 범위로 정의할 수 있습니다.  설치된 .NET 또는 COM 구성 요소, 솔루션에 포함된 Visual Studio 프로젝트를 지정하거나 임의의 어셈블리 또는 형식 라이브러리\(.dll, .tlb, .olb, .exe, 또는 .ocx\)를 지정할 수 있습니다.  참조를 검색하려면 **참조에서 찾기** 상자를 선택합니다.  
  
## 참고 항목  
 [Visual Studio에서 정규식 사용](../ide/using-regular-expressions-in-visual-studio.md)