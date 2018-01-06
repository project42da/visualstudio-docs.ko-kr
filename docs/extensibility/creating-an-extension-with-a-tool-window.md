---
title: "도구 창을 사용 된 확장을 만드는 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 585b0a3a-f85b-4f92-81bb-9ca499bb8a89
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e4e01959df5da96018aa8f1d06fce1076e732096
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-an-extension-with-a-tool-window"></a>도구 창 확장 만들기
이 절차의 VSIX 프로젝트 템플릿을 사용 하는 방법을 배웁니다 및 **사용자 지정 도구 창** 항목 템플릿을 확장 프로그램을 만들려면 도구 창을 사용 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
### <a name="creating-a-tool-window"></a>도구 창을 만드는  
  
1.  라는 VSIX 프로젝트를 **FirstWindow**합니다. VSIX 프로젝트 템플릿을 찾을 수 있습니다는 **새 프로젝트** 대화 상자의 **Visual C# / 확장성**합니다.  
  
2.  프로젝트를 열 때 명명 된 도구 창 항목 템플릿을 추가 **MyWindow**합니다. 에 **솔루션 탐색기**프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 / 새 항목**합니다. 에 **새 항목 추가** 대화 상자에서로 이동 **Visual C# / 확장성** 선택 **사용자 지정 도구 창**합니다. 에 **이름** 창의 맨 아래에 필드, 도구 창 파일 이름 변경 **MyWindow.cs**합니다.  
  
3.  프로젝트를 빌드하고 디버깅을 시작합니다.  
  
     Visual Studio의 실험적 인스턴스가 표시 됩니다. 실험적 인스턴스에 대 한 자세한 내용은 참조 [의 실험적 인스턴스](../extensibility/the-experimental-instance.md)합니다.  
  
4.  실험적 인스턴스에서 이동 **보기 / 다른 창**합니다.  
  
     에 대 한 메뉴 항목 표시 되어야 **MyWindow**합니다. 클릭 합니다.  
  
     도구 창 제목으로 표시 되어야 **MyWindow** 및 단추 말하기가 **Click Me!입니다.**