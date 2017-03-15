---
title: "옵션 대화 상자(Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.toolsoptionspages"
helpviewer_keywords: 
  - "도구 옵션 설정"
  - "옵션 대화 상자"
  - "옵션 대화 상자, 개발 환경"
  - "도구[Visual Studio], 사용자 지정"
ms.assetid: 02b09877-1df1-4531-a0d1-a4ca17c7f857
caps.latest.revision: 19
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 19
---
# 옵션 대화 상자(Visual Studio)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

**옵션** 대화 상자에서는 사용자의 필요에 따라 IDE\(통합 개발 환경\)를 구성할 수 있습니다.  예를 들어, 프로젝트의 기본 저장 위치를 설정하고, 창의 기본 모양과 동작을 변경하며, 일반적으로 사용되는 명령의 바로 가기를 만들 수 있습니다.  개발 언어 및 플랫폼별 옵션도 있습니다.  **도구** 메뉴에서 **옵션**에 액세스할 수 있습니다.  
  
> [!NOTE]
>  대화 상자에서 사용할 수 있는 옵션과 메뉴 명령의 이름 및 위치는 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 옵션 대화 상자의 레이아웃  
 **옵션** 대화 상자는 왼쪽의 탐색 창과 오른쪽의 표시 영역으로 나뉩니다.  탐색 창의 트리 컨트롤에는 환경, 텍스트 편집기, 프로젝트 및 솔루션, 소스 제어 등의 폴더 노드가 있습니다.  포함된 옵션 페이지를 표시하려면 폴더 노드를 확장합니다.  특정 페이지의 노드를 선택하면 표시 영역에 해당 옵션이 나타납니다.  
  
 IDE 기능 옵션은 IDE 기능이 메모리에 로드되어야 탐색 창에 나타나므로,  새로운 세션을 시작할 때는 마지막 세션을 끝낼 때 표시되어 있던 옵션과 다른 옵션이 표시될 수도 있습니다.  프로젝트를 만들거나 특정 응용 프로그램을 사용하는 명령을 실행하면 관련 옵션 노드가 옵션 대화 상자에 추가됩니다.  IDE 기능이 메모리에 남아 있는 동안에는 추가된 옵션을 계속 사용할 수 있습니다.  
  
> [!NOTE]
>  일부 설정 컬렉션에서는 옵션 대화 상자의 탐색 창에 나타나는 페이지 수의 범위를 지정합니다.  **모든 설정 표시**를 선택하면 가능한 페이지를 모두 표시하도록 선택할 수 있습니다.  
  
## 옵션 적용 방법  
 **옵션** 대화 상자에서 확인을 클릭하면 모든 페이지의 설정이 모두 저장되고,  아무 페이지에서나 취소를 클릭하면 다른 **옵션** 페이지에서 변경한 내용을 비롯하여 모든 변경 요청이 취소됩니다.  [옵션 대화 상자, 환경, 글꼴 및 색](../../ide/reference/fonts-and-colors-environment-options-dialog-box.md)의 변경과 같은 일부 옵션 설정 변경 내용은 Visual Studio를 닫았다가 다시 열어야 적용됩니다.  
  
### 모든 설정 표시  
 **모든 설정 표시**를 선택하거나 선택을 취소하면 아직 **확인**을 클릭하지 않았더라도 **옵션** 대화 상자에서 수행한 모든 변경 내용이 적용됩니다.  
  
## 참고 항목  
 [편집기 사용자 지정](../../ide/customizing-the-editor.md)