---
title: "개인 갤러리 | Microsoft Docs"
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
  - "개인 VSIX 갤러리"
  - "VSIX 개인 갤러리"
ms.assetid: b6b3dee7-91c5-4556-9f69-0d56b675e83b
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# 개인 갤러리
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

컨트롤, 템플릿 및 도구를 게시 하 여 개발 하는 공유할 수는 *개인 갤러리* 다음과 같이 조직의 인트라넷에:  
  
-   Atom \(RSS\) 피드를 인트라넷에 적절 하 게 구성 된 중앙 위치 \(리포지토리\)를 만듭니다. 자세한 내용은 [방법: Atom 만들기 개인 갤러리 피드](../extensibility/how-to-create-an-atom-feed-for-a-private-gallery.md)을 참조하세요.  
  
-   개인 갤러리에 설명 하는.pkgdef 파일을 배포 합니다. 비공개 갤러리도 동시에 여러 컴퓨터에 연결 하려는 관리자는이 구성을 사용 하는 것이 좋습니다.  
  
## 확장 및 Visual Studio에서 업데이트에 개인 갤러리를 추가합니다.  
 에 추가할 수 개인 갤러리를 사용할 수 있는 **확장 및 업데이트** Visual Studio에서.  
  
 ![확장 관리자 추가 대화 상자](../extensibility/media/em_adddialog.png "EM\_AddDialog")  
  
#### 확장 및 업데이트에는 개인 갤러리를 추가 하려면  
  
1.  메뉴 모음에서 **도구**, **옵션**을 선택합니다.  
  
2.  에 **환경** 노드를 **확장 및 업데이트**합니다.  
  
3.  **추가** 단추를 선택합니다.  
  
4.  에 **이름** 필드 예를 들어 개인 갤러리에 대 한 이름을 입력 합니다 `My Gallery`합니다.  
  
5.  에 **URL** 필드는 Atom 피드 또는 개인 갤러리를 호스팅하는 SharePoint 사이트의 URL을 입력 합니다.  
  
    1.  호스트 Atom 피드 개인 갤러리에 연결 되 면 URL에는 이와 유사 합니다: http:\/\/www.mywebsite\/mygallery\/atom.xml 합니다.  이 URL을 파일 또는 네트워크 경로 참조할 수 있습니다.  
  
    2.  URL에는 이와 같습니다 호스트 SharePoint 사이트 이면: http:\/\/mysharepoint\/sites\/mygallery\/forms\/AllItems.aspx 합니다.  
  
### 개인 갤러리 관리  
 관리자가 사용할 수 비공개 갤러리도 여러 컴퓨터에 동시에 각 컴퓨터에서 시스템 레지스트리를 수정 하 여. 이를 위해 새 레지스트리 키와 해당 값에 설명 하는.pkgdef 파일을 만듭니다.  이 파일의 형식은 다음과 같습니다.  
  
```  
[$RootPath$\ExtensionManager\Repositories\{UniqueGUID}]  
@={URI}  (REG_SZ)  
Disabled=0 | 1 (DWORD)  
Priority=0 (highest priority) … MaxInt (lowest priority) (DWORD) (uint)  
Protocol=VSGallery|Atom|Sharepoint (REG_SZ)  
DisplayName={DisplayName} (REG_SZ)  
DisplayNameResourceID={ID} (REG_SZ)  
DisplayNamePackageGuid={GUID} (REG_SZ)  
  
```  
  
 자세한 내용은 [방법: 레지스트리 설정을 사용 하 여 개인 갤러리 관리](../extensibility/how-to-manage-a-private-gallery-by-using-registry-settings.md)을 참조하세요.  
  
## 개인 갤러리에서 확장을 설치합니다.  
 검색 하 고에서 개인 갤러리에서 Visual Studio 확장을 설치할 수 **확장 및 업데이트**합니다. 다음 단계 라는 개인 갤러리를 사용 하 여 `My Gallery`합니다.  
  
 ![전용 갤러리를 설치하는 확장 관리자](../extensibility/media/em_.png "EM\_")  
  
#### 검색 하 고 개인 갤러리에서 확장을 설치 합니다.  
  
1.  메뉴 모음에서 **도구**, **확장 및 업데이트**를 선택합니다.  
  
2.  왼쪽된 창에서 선택 **온라인 확장**, 를 선택한 다음 **내 갤러리**합니다.  
  
3.  오른쪽 창에서 확장을 선택한 다음 선택 된 **다운로드** 단추입니다.  
  
## 개인 갤러리에서 확장을 업데이트합니다.  
 새 버전의 Visual Studio 확장은 개인 갤러리에 게시 된, 설치 된 확장 업데이트할 수 있습니다. 다음 단계 라는 개인 갤러리를 사용 하 여 `My Repository`합니다.  
  
 ![확장 관리자 전용 갤러리 업데이트](../extensibility/media/em_update.png "EM\_Update")  
  
#### 개인 갤러리에서 설치 된 확장을 업데이트 하려면  
  
1.  메뉴 모음에서 **도구**, **확장 및 업데이트**를 선택합니다.  
  
2.  왼쪽된 창에서 선택 **업데이트**, 를 선택한 다음 **내 저장소**합니다.  
  
3.  오른쪽 창에서 확장을 선택한 다음 선택 된 **업데이트** 단추입니다.  
  
## 참고 항목  
 [Visual Studio 확장 찾기 및 사용](../ide/finding-and-using-visual-studio-extensions.md)   
 [배송 Visual Studio 확장](../extensibility/shipping-visual-studio-extensions.md)