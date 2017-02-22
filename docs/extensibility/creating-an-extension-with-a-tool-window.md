---
title: "확장 도구 창 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 585b0a3a-f85b-4f92-81bb-9ca499bb8a89
caps.latest.revision: 5
caps.handback.revision: 5
ms.author: "gregvanl"
manager: "ghogen"
---
# 확장 도구 창 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 절차에서는 VSIX 프로젝트 템플릿을 사용 하는 방법을 알아봅니다 및 **사용자 지정 도구 창** 항목 템플릿을 확장 프로그램을 만들려면 도구 창을 사용 합니다.  
  
## 사전 요구 사항  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)을 참조하세요.  
  
### 도구 창 만들기  
  
1.  라는 이름의 VSIX 프로젝트 **FirstWindow**합니다. VSIX 프로젝트 템플릿을 찾을 수는 **새 프로젝트** 대화 상자의 **Visual C\# \/ 확장성**합니다.  
  
2.  프로젝트를 열면 도구 창 항목 템플릿을 추가 **FirstWindow**합니다. 에 **솔루션 탐색기**, 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 \/ 새 항목**합니다. 에 **새 항목 추가** 대화 상자에서 이동 **Visual C\# \/ 확장성** 선택한 **사용자 지정 도구 창**합니다. 에 **이름** 창의 맨 아래에 필드, 도구 창 파일 이름 변경 **FirstWindow.cs**합니다.  
  
3.  프로젝트를 빌드하고 디버깅을 시작합니다.  
  
     Visual Studio의 실험적 인스턴스가 표시 됩니다. 실험적 인스턴스에서 대 한 자세한 내용은 참조 [실험적 인스턴스](../extensibility/the-experimental-instance.md)합니다.  
  
4.  실험적 인스턴스를에서으로 **보기 \/ 다른 창**합니다.  
  
     에 대 한 메뉴 항목 표시 되어야 **FirstWindow**합니다. 클릭 합니다.  
  
     도구 창 제목으로 표시 되어야 **FirstWindow** 및 단추 말하기가 **Click Me\!.**