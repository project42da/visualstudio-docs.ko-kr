---
title: "기본 도구 창 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Visual Studio SDK, 도구 창"
  - "도구 창, IDE에서 만들기"
ms.assetid: 1e96cf07-bde4-445b-bcd0-48cadb351dde
caps.latest.revision: 12
caps.handback.revision: 12
manager: "douge"
---
# 기본 도구 창 만들기
도구 창은 일반적인 Visual Studio로, **솔루션 탐색기**, **작업 목록**, **오류 목록** 및 **출력** 창이 있는 모든 도구 창입니다. 모든 도구 창은 동일한 방식으로 IDE에서 도킹될 수 있습니다. 예측 가능한 도킹을 통해 사용자는 작업 및 정보를 효율적으로 관리할 수 있습니다.  
  
 Visual Studio 패키지 템플릿은 간단한 도구 창의 기본 구현을 만듭니다.  
  
### Visual Studio 패키지 템플릿을 사용하여 도구 창을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자에서 **기타 프로젝트 형식**, **확장성**을 차례로 클릭합니다.  
  
3.  **템플릿** 창에서 **Visual Studio 패키지**를 클릭합니다.  
  
4.  **위치** 상자에서 VSPackage에 대한 파일 경로를 입력합니다.  
  
5.  **이름** 상자에서 솔루션에 대한 이름을 입력하고 **확인**을 클릭하여 템플릿을 시작합니다.  
  
6.  **프로그래밍 언어 선택** 페이지에서 C\# 또는 Visual Basic을 선택합니다. 템플릿에서 어셈블리에 서명할 key.snk 파일을 생성하도록 합니다. 또는 고유한 키 파일을 **찾아봅니다**. 템플릿에서 키 파일의 복사본을 만들고 key.snk라는 이름을 지정합니다.  
  
7.  **VSPackage 기본 정보** 페이지에서 VSPackage에 대한 세부 정보를 지정하거나 기본값을 적용합니다. 자세한 내용은 [연습: Visual Studio 패키지 템플릿을 사용하여 메뉴 명령 만들기](../Topic/Walkthrough:%20Creating%20a%20Menu%20Command%20By%20Using%20the%20Visual%20Studio%20Package%20Template.md)을 참조하세요.  
  
8.  **VSPackage 옵션 선택** 페이지에서 도구 창을 확인합니다.  
  
9. 도구 창 옵션 페이지의 **창 이름** 상자에 제목 표시줄의 이름을 입력합니다. 이 이름은 도구 창의 메뉴 명령에 대한 표시 텍스트로 사용됩니다. 메뉴 명령이 **보기** 메뉴의 **다른 창** 하위 메뉴에 추가됩니다.**명령 ID** 상자에서 도구 창에 대한 명령 ID를 입력하거나 기본값을 적용합니다.  
  
10. 지정한 폴더에 VSPackage를 만들려면 **마침**을 클릭합니다.  
  
### 도구 창을 테스트하려면  
  
1.  **보기** 메뉴에서 **다른 창**을 가리킨 다음 도구 창 명령을 클릭합니다.**Click Me\!** 단추가 포함된 도구 창이 나타납니다.  
  
2.  단추를 클릭합니다. 메시지가 다음 텍스트와 함께 표시됩니다.  
  
     \[Company.\<VSPackage 이름\>.MyControl\].button1\_Click\(\)에 있습니다.  
  
## 참고 항목  
 [프로그래밍 방식으로 도구 창 열기](../misc/opening-a-tool-window-programmatically.md)   
 [VSPackage Essentials](../misc/vspackage-essentials.md)