---
title: "방법: Visual Studio 확장을 업데이트 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "업데이트 패키지"
  - "확장 업데이트"
  - "새 패키지 버전"
ms.assetid: 93f79774-7b79-4dd6-94ad-13698f72c257
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# 방법: Visual Studio 확장을 업데이트
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

사용 하 여 시스템에 Visual Studio 확장을 업데이트할 수 있습니다 **확장 및 업데이트** 업데이트 된 버전을 설치 합니다. 확장의 업데이트 된 버전을 만들면 VSIX 매니페스트의 버전 번호를 증분 하 여 업데이트 되었음을 표시할 수 있습니다.  
  
 들어오는 확장의 VSIX 매니페스트 같습니다 업데이트가 설치 됩니다 `ID` 하나씩 설치 및 더 높은 `Version` 수 있습니다. 하는 경우는 `Version` 번호는 동일 하거나 이하인 패키지를 설치할 수 없습니다. 하는 경우는 `ID` 값이 일치 하지 않으면, 아직 설치 되지 않은 패키지는 별도 확장으로 인식 됩니다.  
  
 개발 하는 동안 충돌을 방지 하려면 이전 버전의 진행 중인 확장을 제거 하 고도 제거 하거나 해제 하 다른 잠재적 충돌 하는 확장은 것이 좋습니다.  
  
### 시스템에서 확장을 업데이트 하려면  
  
1.  **도구** 메뉴에서 **확장 및 업데이트**를 클릭합니다.  
  
2.  왼쪽된 창에서 **업데이트**합니다.  
  
3.  가운데 창에서 설치할 업데이트를 클릭 합니다.  
  
     업데이트 된 확장의 버전 번호는 다른 정보와 함께 오른쪽 창에 표시 됩니다.  
  
4.  오른쪽 창의 아래쪽 클릭 **업데이트**합니다.  
  
### 확장의 업데이트를 게시 하려면  
  
1.  Visual Studio에서 업데이트 하려는 확장에 대 한 솔루션을 엽니다. 변경 내용을 확인 합니다.  
  
    > [!IMPORTANT]
    >  서명 되지 않은 모든 사용자 확장이 자동으로 업데이트 되지 않습니다. 항상 확장 프로그램에 서명 해야 합니다.  
  
2.  **솔루션 탐색기**, source.extension.manifest를 엽니다.  
  
3.  매니페스트 디자이너에서 숫자 값을 늘려는 **버전** 필드입니다.  
  
4.  솔루션을 저장 하 고 빌드하십시오.  
  
5.  \(프로젝트의 \\bin\\Debug\\ 폴더\)에 새.vsix 파일을 업로드는 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkID=123847) 웹 사이트입니다.  
  
     확장의 이전 버전을 가진 사용자를 열면 **확장 및 업데이트**, 새 버전에 표시 됩니다는 **업데이트** 목록에서 도구는 자동으로 업데이트를 찾도록 설정 합니다.  
  
     맨 아래에 업데이트에 대 한 자동 확인을 해제 하거나 설정할 수는 **업데이트** 창 \(**사용 가능한 업데이트의 자동 검색을 활성화\/비활성화**\), 변경 내용을 **업데이트 확인** 에서 설정 **도구 \/ 옵션 \/ 환경 \/ 확장 및 업데이트**.  
  
    > [!NOTE]
    >  Visual Studio 2015 업데이트 2 부터는 지정할 수 있습니다 \(에서 **도구 \/ 옵션 \/ 환경 \/ 확장 및 업데이트**\) 사용자별 확장, 모든 사용자 확장 또는 모두 \(기본 설정\)에 대 한 자동 업데이트를 것인지 합니다.  
  
## 참고 항목  
 [VSIX 패키지에 대 한 분석](../extensibility/anatomy-of-a-vsix-package.md)   
 [Visual Studio 확장 찾기 및 사용](../ide/finding-and-using-visual-studio-extensions.md)