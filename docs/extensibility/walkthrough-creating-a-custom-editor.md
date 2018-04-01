---
title: '연습: 사용자 지정 편집기 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], custom - create
ms.assetid: d090abb6-d99f-4083-a3db-cd16bf81ce7d
caps.latest.revision: 17
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9e8ea75cb96b36f885a55cbf9f174394379dc05a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-custom-editor"></a>연습: 사용자 지정 편집기 만들기
VSPackage 프로젝트 템플릿으로 c + +에서 간단한 사용자 지정 편집기를 만들 수 있습니다.  VSPackage 프로젝트 템플릿으로 더 이상 C# 또는 Visual Basic 프로젝트를 지원합니다. 자세한 내용은 참조 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="the-visual-studio-package-project-template"></a>Visual Studio 패키지 프로젝트 템플릿  
 Visual Studio 패키지 프로젝트 템플릿은에서 확인할 수 있습니다는 **새 프로젝트** c + + 확장성 폴더에서 대화 상자  
  
### <a name="to-create-a-vspackage-using-the-visual-studio-package-template"></a>Visual Studio 패키지 템플릿을 사용 하 여 VSPackage를 만들려면  
  
1.  Visual Studio 패키지 템플릿을 사용 하 여 프로젝트를 만듭니다.  
  
2.  선택 된 **사용자 지정 편집기** 옵션 **다음**합니다. **편집기 옵션** 페이지가 표시 됩니다.  
  
3.  편집기의 이름을 입력 하 고 **편집기 이름** 상자입니다. 파일 확장명에 편집기와 연결 하려면을 입력에서 **파일 확장명** 상자입니다. 편집기는이 확장을 사용 하 여 파일에 사용할 수 있습니다. 파일 확장명은 Windows에 대 한만, Visual Studio에 등록 됩니다. 편집기를 사용 하 여 만든 새 문서에 대 한 기본 파일 이름을 입력 된 **기본 파일 이름은** 상자입니다.  
  
4.  지정한 폴더에 VSPackage를 만들려면 **마침** 을 클릭합니다.  
  
### <a name="to-test-your-custom-editor"></a>사용자 지정 편집기를 테스트 하려면  
  
1.  에 **파일** 메뉴에서 **새로** 클릭 하 고 **파일**합니다.  
  
2.  에 **설치 된 템플릿** 의 창은 **새 파일** 대화 상자에서 방금 등록 한 파일 템플릿을 다음 파일 형식입니다.  
  
3.  클릭 **열려** 를 보고 하 여 문서를 편집 합니다.  
  
     편집기는 잘라내기-붙여넣기, 찾기 및 바꾸기 및 오픈 로드 작업을 지원합니다.  
  
## <a name="see-also"></a>참고 항목  
 [VSPackage](../extensibility/internals/vspackages.md)