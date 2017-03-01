---
title: "연습: Visual Studio 확장을 게시 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publishing web controls
- web controls, publishing
ms.assetid: a7816161-0490-4043-86f5-0f7331ed83b3
caps.latest.revision: 17
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: 574af4ff2b3858201c13121475de02a763572f6b
ms.openlocfilehash: fcfb0724b89d60553d6686a0705ab1e9459014ce
ms.lasthandoff: 02/22/2017

---
# <a name="walkthrough-publishing-a-visual-studio-extension"></a>연습: Visual Studio 확장 게시
이 연습에서는 Visual Studio 확장 Visual Studio 갤러리에 게시 하는 방법을 보여 줍니다. 갤러리에 확장을 추가 하면 개발자가 사용할 수 **확장 및 업데이트** 검색할 수 있는 새로운 기능과 업데이트 된 확장 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 참조 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)합니다.  
  
## <a name="create-a-visual-studio-extension"></a>Visual Studio 확장 기능 만들기  
 이 경우 기본 VSPackage 확장을 사용 합니다 하지만 동일한 단계는 모든 종류의 확장에 대해 유효 합니다.  
  
1.  C# 라는 VSPackage를 만듭니다 `TestPublishing` 메뉴 명령을 포함 합니다. 자세한 내용은 참조 [메뉴 명령을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-a-menu-command.md)합니다.  
  
## <a name="test-the-extension"></a>확장을 테스트 합니다  
 확장을 배포 하기 전에 빌드하고 테스트 하 Visual Studio의 실험적 인스턴스에서 올바르게 설치 되어 있는지 확인 합니다.  
  
1.  Visual Studio에서 디버깅을 시작 합니다. Visual Studio의 실험적 인스턴스를 엽니다.  
  
2.  실험적 인스턴스에서에서 이동 하는 **도구** 메뉴를 클릭 **확장 관리자**합니다. TestPublishing 확장 가운데 창에 표시 되어야 하 고 사용 하도록 설정.  
  
3.  에 **도구** 메뉴에서 테스트 명령 참조 해야 합니다.  
  
## <a name="publish-the-extension-to-the-visual-studio-gallery"></a>Visual Studio 갤러리에 확장 게시  
 이제 Visual Studio 갤러리에 확장 프로그램을 게시할 수 있습니다.  
  
1.  확장 프로그램의 릴리스 버전 빌드 및 최신 상태 인지 확인 합니다.  
  
2.  웹 브라우저에서 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkId=194329) 웹 사이트를 엽니다.  
  
3.  오른쪽 위 모서리에서 클릭 **SIGN IN**합니다.  
  
4.  Microsoft 계정을 사용하여 로그인합니다. Microsoft 계정이 없는 경우이 시점에서 만들 수 있습니다.  
  
5.  **업로드**를 클릭합니다.  
  
6.  **1 단계: 확장 형식**선택, **도구** 클릭 하 고 **다음**합니다.  
  
7.  **2 단계: 업로드할**, Visual Studio 갤러리에 직접 업로드 하거나 자신의 웹 사이트에 대 한 링크 추가 하도록 선택할 수 있습니다. 이 경우에 선택 **내 도구를 업로드 하려는**합니다. **control 선택** 상자가 나타납니다. 클릭 **찾아보기** TestPublish.vsix 프로젝트의 \bin\Release 폴더를 선택 합니다. **다음**을 클릭합니다.  
  
8.  **3 단계: 기본 정보**, source.extension.vsixmanifest 파일의 필드가 표시 됩니다. 적절 한 선택 **범주** 추가 **태그** 확장 프로그램을 찾을 수 있도록 합니다. 더 자세한 요약 및 description (설명 적어도 280 자 이어야 함)을 추가 하 고 좋습니다. 둡니다 **확장 형식** 으로 **는 Microsoft 확장** 및 **범주 비용** 으로 **평가판**합니다.  
  
9. 페이지 맨 아래에 기고 약관을 읽고 확인 **동의**합니다.  
  
10. 클릭 **작성 글 만들기**합니다. 이 확장 했을 경우에 페이지가 아직 게시 되지 않았다는 메시지와 함께 Visual Studio 갤러리에서 페이지를 표시 합니다.  
  
11. **게시**를 클릭합니다.  
  
12. 확장 프로그램에 대 한 Visual Studio 갤러리를 검색 합니다. TestPublish 확장에 대 한 목록에 표시 됩니다.  
  
## <a name="install-the-extension-from-the-visual-studio-gallery"></a>Visual Studio 갤러리에서 확장을 설치 합니다.  
 확장을 게시 했으므로 Visual Studio에서 설치 하 고 테스트할 수 있습니다.  
  
1.  Visual Studio에서에 **도구** 메뉴를 클릭 하 여 **확장 및 업데이트**합니다.  
  
2.  클릭 **온라인** TestPublish 검색 합니다. TestPublish 확장에 대 한 목록에 표시 됩니다.  
  
3.  **다운로드**를 클릭합니다. 확장을 다운로드한 후 **설치**를 클릭합니다.  
  
4.  설치를 완료 하려면 Visual Studio를 다시 시작 합니다.  
  
## <a name="removing-the-extension"></a>확장 제거  
 Visual Studio 갤러리 및 사용자의 컴퓨터에서 확장을 제거할 수 있습니다.  
  
#### <a name="to-remove-the-extension-from-the-visual-studio-gallery"></a>Visual Studio 갤러리에서 확장을 제거 하려면  
  
1.  열기는 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkId=194329) 웹 사이트입니다.  
  
2.  센터에서 클릭 **My 확장**합니다. TestPublish 목록을 표시 됩니다.  
  
3.  클릭 **삭제**합니다.  
  
#### <a name="to-remove-the-extension-from-your-computer"></a>컴퓨터에서 확장을 제거 하려면  
  
1.  Visual Studio의 **도구** 메뉴에서 **확장 관리자**를 클릭합니다.  
  
2.  TestPublish를 선택한 다음 클릭 **제거**합니다.  
  
3.  제거를 완료 하려면 Visual Studio를 다시 시작 합니다.

