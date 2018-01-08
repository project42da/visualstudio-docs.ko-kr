---
title: "방법: Visual Studio 확장을 업데이트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- update package
- update extension
- new package version
ms.assetid: 93f79774-7b79-4dd6-94ad-13698f72c257
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 46b540f1c5ba5b345464948170287d2b354b7a0e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-update-a-visual-studio-extension"></a>방법: Visual Studio 확장을 업데이트
사용 하 여 시스템에서 Visual Studio 확장을 업데이트 **확장명 및 업데이트** 업데이트 된 버전을 설치 합니다. 확장의 업데이트 된 버전을 만들면 VSIX 매니페스트의 버전 번호가 증가 하 여 업데이트 되었음을 표시할 수 있습니다.  
  
 들어오는 확장의 VSIX 매니페스트가 동일한 업데이트가 설치 된 `ID` 하나씩 설치 및 더 높은 `Version` 번호입니다. 경우는 `Version` 번호는 동일 하거나 이하인 패키지를 설치할 수 없습니다. 경우는 `ID` 값이 일치 하지 않으면, 아직 설치 되지 않은 패키지는 별도 확장 프로그램으로 인식 됩니다.  
  
 개발 하는 동안 충돌을 방지 하려면, 진행 중인 확장의 이전 버전을 제거 하 고도 제거 하거나 해제 하 기타 잠재적으로 충돌 하는 확장은 것이 좋습니다.  
  
### <a name="to-update-an-extension-on-your-system"></a>시스템에서 확장을 업데이트 하려면  
  
1.  **도구** 메뉴에서 **확장 및 업데이트**를 클릭합니다.  
  
2.  왼쪽된 창에서 클릭 **업데이트**합니다.  
  
3.  가운데 창에서 설치할 업데이트를 클릭 합니다.  
  
     업데이트 된 확장의 버전 번호는 다른 정보와 함께, 오른쪽 창에 표시 됩니다.  
  
4.  오른쪽 창의 맨 아래에 클릭 **업데이트**합니다.  
  
### <a name="to-publish-an-update-of-an-extension"></a>확장의 업데이트를 게시 하려면  
  
1.  Visual Studio에서 업데이트 하려는 확장에 대 한 솔루션을 엽니다. 변경 내용을 확인 합니다.  
  
    > [!IMPORTANT]
    >  서명 되지 않은 모든 사용자 확장이 자동으로 업데이트 되지 않습니다. 항상 확장 프로그램에 서명 해야 합니다.  
  
2.  **솔루션 탐색기**, source.extension.manifest를 엽니다.  
  
3.  매니페스트 디자이너에서 숫자 값을 늘리십시오는 **버전** 필드입니다.  
  
4.  솔루션을 저장 하 고 빌드하십시오.  
  
5.  (프로젝트의 \bin\Debug\ 폴더에 있음)에서 새.vsix 파일을 업로드는 [Visual Studio 마켓플레이스](https://marketplace.visualstudio.com/vs) 웹 사이트입니다.  
  
     확장의 이전 버전을 가진 사용자가 열 때 **확장명 및 업데이트**, 새 버전에 표시 됩니다는 **업데이트** 목록 도구를 자동으로 업데이트 될 때까지 찾도록 설정 됩니다.  
  
     맨 아래에 업데이트에 대 한 자동 확인을 해제 하거나 설정할 수 있습니다는 **업데이트** 창 (**사용 가능한 업데이트의 자동 검색 설정/해제**), 변경 내용을 **확인 업데이트** 에서 설정 **도구 / 옵션 / 환경 / 확장명 및 업데이트**합니다.  
  
    > [!NOTE]
    >  Visual Studio 2015 업데이트 2부터 사용자별 확장, 모든 사용자 확장 또는 둘 다(기본 설정)에 대해 자동 업데이트를 사용할지를 지정할 수 있습니다(**도구/옵션/환경/확장 및 업데이트**).  
  
## <a name="see-also"></a>참고 항목  
 [VSIX 패키지 분석](../extensibility/anatomy-of-a-vsix-package.md)   
 [Visual Studio 확장 찾기 및 사용](../ide/finding-and-using-visual-studio-extensions.md)
