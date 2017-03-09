---
title: "방법: Visual C++의 키워드 정의 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "사용자 키워드"
  - "예약어, 사용자 정의된 키워드"
  - "사용자 정의된 키워드"
  - "예약된 키워드, 사용자 정의"
  - "usertype.dat"
  - "키워드[C++], 사용자 정의"
ms.assetid: 2dfcf343-e861-4bde-b5a4-7deb6773d9c8
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 방법: Visual C++의 키워드 정의
키워드는 특별한 의미가 있는 미리 정의된 예약된 식별자입니다. 따라서 프로그램에서 키워드를 식별자로 사용할 수 없습니다. 그러나 Visual C\+\+에서 사용할 고유 키워드를 정의할 수 있고 사용자 지정된 구문 색 지정을 키워드에 할당할 수 있습니다. 구문 색 지정은 코드의 구조 및 상태에 대한 시각 정보를 제공합니다.  
  
### 사용자 고유의 Visual C\+\+ 키워드를 정의하려면  
  
1.  Visual Studio [코드 및 텍스트 편집기](http://msdn.microsoft.com/ko-kr/508e1f18-99d5-48ad-b5ad-d011b21c6ab1) 또는 Notepad.exe를 사용하여 이름이 `usertype.dat`인 텍스트 전용 파일을 만듭니다.  
  
2.  `usertype.dat`에서 별도의 줄에 사용자 정의된 각 키워드를 입력합니다.  
  
3.  devenv.exe를 포함하는 디렉터리에 `usertype.dat`를 저장합니다. 기본적으로 해당 디렉터리의 경로는 *\<드라이브\>*:\\Program Files\\[!INCLUDE[TLA#tla_visualstu](../misc/includes/tlasharptla_visualstu_md.md)] *\<major.minor 버전 번호\>*\\Common7\\[!INCLUDE[TLA2#tla_ide](../misc/includes/tla2sharptla_ide_md.md)]입니다. 해당 디렉터리는 기본적으로 읽기 전용이기 때문에 `usertype.dat`를 저장하려면 관리자 자격 증명이 필요합니다.  
  
4.  Visual Studio를 종료한 다음 다시 시작합니다.  
  
    > [!NOTE]
    >  초기화하는 동안 읽기 때문에 편집 세션 중에 `usertype.dat` 파일의 이름을 바꾸거나 다시 로드할 수 없습니다. 구문 색 지정 메커니즘에서 `usertype.dat` 파일을 마지막에 확인하므로 이전에 정의된 모든 색 설정이 우선 적용됩니다.  
  
5.  **도구** 메뉴에서 **옵션**을 클릭합니다.**옵션** 대화 상자에서 **환경**을 클릭한 다음 **글꼴 및 색**을 클릭하고 다음으로 **표시 항목:** 목록에서 **C\/C\+\+ 사용자 키워드**를 클릭합니다.  
  
6.  [옵션 대화 상자, 환경, 글꼴 및 색](../ide/reference/fonts-and-colors-environment-options-dialog-box.md)에 설명된 대로 사용자 정의 키워드의 글꼴 및 색 속성을 설정합니다.  
  
 자세한 내용은 [C\+\+ 키워드](/visual-cpp/cpp/keywords-cpp)을 참조하세요.  
  
## 참고 항목  
 [사용자 그룹의 멤버로 실행](/visual-cpp/top/running-as-a-member-of-the-users-group)   
 [기본 바로 가기 키](../ide/default-keyboard-shortcuts-in-visual-studio.md)