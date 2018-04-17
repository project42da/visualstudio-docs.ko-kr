---
title: '연습: Visual Studio 확장을 게시 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- publishing web controls
- web controls, publishing
ms.assetid: a7816161-0490-4043-86f5-0f7331ed83b3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f823334f3686bdba3406daac69b2a98d203780a7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-publishing-a-visual-studio-extension"></a>연습: Visual Studio 확장 게시

이 연습에서는 Visual Studio 마켓플레이스를 Visual Studio 확장을 게시 하는 방법을 보여 줍니다. 마켓플레이스 확장 프로그램을 추가 하면 개발자가 사용할 수 **확장명 및 업데이트** 새로 추가 되거나 업데이트 된 확장을 검색할 수 있는 하 합니다.

## <a name="prerequisites"></a>전제 조건

 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.

## <a name="create-a-visual-studio-extension"></a>Visual Studio 확장명 만들기

이 경우 기본 VSPackage 확장 프로그램을 사용 합니다 하지만 동일한 단계가 모든 종류의 확장에 대 한 유효 합니다.

1. 메뉴 명령에 "TestPublish" 라는 C#에서 VSPackage를 만듭니다. 자세한 내용은 참조 [첫 번째 확장 프로그램을 만드는: Hello World](../extensibility/extensibility-hello-world.md)합니다.

## <a name="package-your-extension"></a>확장을 패키지합니다

1. 확장 vsixmanifest 제품 이름, 만든이 및 버전에 대 한 올바른 정보로 업데이트 합니다.

  ![확장 vsixmanifest 업데이트](media/update-extension-vsixmanifest.png)

2. 확장 프로그램에서 작성 **릴리스** 모드입니다. 이제 확장 \bin\Release 폴더에 VSIX로 패키지 됩니다.

3. VSIX 설치를 확인 하려면 클릭 하는 두 번 수 있습니다.

## <a name="test-the-extension"></a>확장을 테스트 합니다

 확장을 배포 하기 전에 빌드하고 테스트 하에서 Visual Studio의 실험적 인스턴스가 제대로 설치 되었는지 확인 합니다.

1. Visual Studio에서 디버깅을 시작 합니다. Visual Studio의 실험적 인스턴스를 엽니다.

2. 실험적 인스턴스에서에서 이동 하는 **도구** 메뉴 **확장명 및 업데이트 중...** . TestPublish 확장 가운데 창에 표시 되어야 하 고 사용 하도록 설정 합니다.

3. 에 **도구** 메뉴에서 테스트 명령을 볼 수 있어야 합니다.

## <a name="publish-the-extension-to-the-visual-studio-marketplace"></a>Visual Studio 마켓플레이스로 확장 게시

1. 확장 프로그램의 릴리스 버전 빌드 하며 최신 인지 확인 합니다.

2. 웹 브라우저를 열고는 [Visual Studio 마켓플레이스](https://marketplace.visualstudio.com/vs) 웹 사이트입니다.

3. 오른쪽 위 모서리에서 클릭 **로그인**합니다.

4. Microsoft 계정을 사용하여 로그인합니다. Microsoft 계정이 없는 경우이 시점에서 만들 수 있습니다.

5. 클릭 **확장 게시**합니다.  이 모든 확장에 대 한 관리 페이지를 탐색 합니다.  게시자 계정에 없을 경우 지금 새로 만들려면 라는 메시지가 표시 됩니다.

  ![마켓플레이스로 업로드](media/upload-to-marketplace.png)

6. 확장을 업로드 하는 데 사용할 게시자를 선택 합니다.  왼쪽에 나열 된 게시자 이름을 클릭 하 여 게시자를 변경할 수 있습니다.  클릭 **새 확장** 선택 **Visual Studio**합니다.

7. **1: 확장 업로드**를 자신의 웹 사이트에 링크를 추가 하거나 Visual Studio 마켓플레이스에 직접 VSIX 파일을 업로드 하도록 선택할 수 있습니다. 이 경우 TestPublish.vsix 우리의 확장을 업로드 합니다.  끌어 및 확장 프로그램을 삭제 하거나 사용는 **클릭** 링크는 파일을 찾아봅니다.  확장 프로그램 프로젝트의 \bin\Release 폴더에서 찾을 수 있습니다.  **계속**을 클릭합니다.

8. **2: 확장 세부 정보를 제공**, 일부 필드는 자동으로 채워진 해당 확장에서 source.extension.vsixmanifest 파일에서 합니다.  각각에 대 한 자세한 내용은 아래 확인할 수 있습니다.

    * **내부 이름** 확장의 세부 정보 페이지의 URL에 사용 됩니다. 예를 들어 게시자 이름이 "myname" 아래에서 확장을 게시 하 고 "myextension" 하 고 내부 이름을 지정 하 됩니다의 URL에 "marketplace.visualstudio\.com/items?itemName=myname.myextension" 확장 프로그램에 대 한 세부 정보 페이지입니다.
    
    * **표시 이름** 확장 합니다.  이 자동으로 채워진에서 source.extension.vsixmanifest 파일입니다.
   
    * **버전** 업로드 하는 확장의 번호입니다.  이 자동으로 채워진에서 source.extension.vsixmanifest 파일입니다.
    
    * **VSIX ID** 확장 프로그램에 대 한 Visual Studio를 사용 하는 고유 식별자입니다.  자동 업데이트 될 확장 프로그램을 원하는 경우 이것이 필요 합니다.  이 자동으로 채워진에서 source.extension.vsixmanifest 파일입니다.
    
   * **로고** 확장 프로그램에 대해 사용 되는 합니다.  제공 된 경우 source.extension.vsixmanifest 파일에서 자동으로 채워진 수 있습니다.
    
    * **간단한 설명** 확장 프로그램에서 수행 하는 작업입니다.  Source.extension.vsixmanifest 파일에서 자동으로 채워진 수 있습니다.
    
    * **개요** 스크린샷 및 확장 프로그램에서 수행 하는 작업에 대 한 자세한 정보를 포함 하는 데는 합니다.
    
    * **지원 되는 Visual Studio 버전** 어떤 버전의 Visual Studio 확장 프로그램은 작동을 선택할 수 있습니다.  확장 프로그램은 해당 버전에만 설치 됩니다.
    
    * **지원 되는 Visual Studio 버전** 어떤 버전의 Visual Studio 확장 프로그램은 작동을 선택할 수 있습니다.  확장 프로그램은 이러한 버전에만 설치 됩니다.
    
    * **형식**.  가장 일반적인 유형의 확장은 **도구**합니다.
    
    * **범주**합니다.  확장 프로그램에 가장 적합 한 되는 최대 3 개의 선택 합니다.
    
    * **태그** 는 데 도움이 되는 키워드 찾을 확장 합니다. 태그는 시장에서 확장 프로그램의 검색 관련성을 높일 수 있습니다.
    
    * **범주 가격** 비용 확장 프로그램입니다.
    
    * **소스 코드 리포지토리** 커뮤니티와 소스 코드에 대 한 링크를 공유할 수 있습니다.
    
    * **확장 프로그램에 대 한 질문 및 답변 허용** 사용자 확장 항목 페이지에서 질문을 종료할 수 있습니다.

9. 클릭 **저장 후 업로드**합니다. 그러면 게시자에 다시 관리 페이지입니다.  확장 아직 게시 되지 않았습니다.  확장 프로그램을 게시 하려면 단추로 클릭 하 여 확장 고 **공개**합니다.  어떻게 확장 버리면 마켓플레이스에서 선택 하 여 볼 수 있습니다 **보기 확장**합니다.  인수 번호에 대 한 클릭 **보고서**합니다.  확장 프로그램을 변경 하려면 클릭 **편집*합니다.

  ![확장 항목 메뉴](media/extension-entry-menu.png)

10. 클릭 한 후 **공개**, 확장 프로그램는 현재 공용입니다.  확장 프로그램에 대 한 Visual Studio 마켓플레이스를 검색 합니다.

## <a name="add-additional-users-to-manage-your-publisher-account"></a>게시자 계정을 관리 하는 추가 사용자를 추가 합니다.

마켓플레이스 추가 사용자에 게 액세스 하 고 게시자 계정 관리에 대 한 권한 부여를 지원 합니다.

1. 사용자가 더 추가 하려면 게시자 계정으로 이동 합니다.

2. 선택 **멤버** 을 클릭할 **추가**

  ![추가 사용자를 추가 합니다.](media/add-users.png)

3. 추가 하 고 적절 한 수준의 액세스를 부여 하려면 사용자의 전자 메일 주소를 지정할 수 있습니다 **역할 선택**합니다.  다음 중에서 선택할 수 있습니다.

  * **Creator**: 사용자 확장을 게시 하지만 없습니다 보거나 관리할 수 있는 다른 사용자가 게시 된 확장이 있습니다.
  
  * **판독기**: 사용자 확장 하지만 없습니다 게시 보거나 관리할 수 있는 확장 합니다.
  
  * **참가자**: 사용자 수를 게시 및 확장을 관리 하지만 없습니다 게시자 설정을 편집 또는 관리 액세스 합니다.
  
  * **소유자**: 사용자 수 게시 및 확장을 관리, 게시자 설정을 편집 및 액세스를 관리 합니다.
  
## <a name="install-the-extension-from-the-visual-studio-marketplace"></a>Visual Studio 마켓플레이스에서 확장을 설치 합니다.

확장을 게시 했으므로 Visual Studio에서 설치 하 고 테스트할 수 있습니다.

1. Visual Studio에서에 **도구** 메뉴를 클릭 하 여 **확장명 및 업데이트 중...** .

2. 클릭 **온라인** TestPublish 검색할 합니다.

3. **다운로드**를 클릭합니다. 확장 한 다음 설치를 위해 예약 됩니다.

4. 설치를 완료 하려면 Visual Studio의 모든 인스턴스를 닫습니다.

## <a name="remove-the-extension"></a>확장 제거

Visual Studio 마켓플레이스 및 컴퓨터에서 확장을 제거할 수 있습니다.

### <a name="to-remove-the-extension-from-the-visual-studio-marketplace"></a>Visual Studio 마켓플레이스에서 확장을 제거 하려면

1. 열기는 [Visual Studio 마켓플레이스](https://marketplace.visualstudio.com/vs) 웹 사이트입니다.

2. 오른쪽 상단 모서리에서 클릭 **게시** 확장 합니다.  TestPublish 게시 하는 데 사용 된 게시자를 선택 합니다.  TestPublish 목록이 표시 됩니다.

3. 확장 프로그램 항목을 마우스 오른쪽 단추로 클릭 하 고 클릭 **제거** 확장을 제거할 것인지 확인 해야 합니다.  **확인**을 클릭합니다.

### <a name="to-remove-the-extension-from-your-computer"></a>컴퓨터에서 확장을 제거 하려면

1. Visual Studio에서에 **도구** 메뉴를 클릭 하 여 **확장 및 업데이트 중...** .

2. TestPublish를 선택한 다음 클릭 **제거**합니다. 확장 한 다음 제거를 위해 예약 됩니다.

3. 제거를 완료 하려면 Visual Studio의 모든 인스턴스를 닫습니다.
