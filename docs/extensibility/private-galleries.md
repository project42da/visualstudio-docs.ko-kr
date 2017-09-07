---
title: "전용 갤러리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSIX galleries, private
- private galleries, VSIX
ms.assetid: b6b3dee7-91c5-4556-9f69-0d56b675e83b
caps.latest.revision: 10
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
ms.translationtype: MT
ms.sourcegitcommit: 8ce054bf6149f0224785f4c3cd9274e86dc09d04
ms.openlocfilehash: e4c49a19a9befad5d90b9526842786f49af0851b
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---
# <a name="private-galleries"></a>Private Galleries
컨트롤, 템플릿 및 하도록 게시 하 여 개발 하는 도구를 공유할 수는 *전용 갤러리* 다음과 같이 조직에 대 한 인트라넷에:  
  
-   Atom (RSS) 피드를 인트라넷에 적절 하 게 구성 된 중앙 위치 (리포지토리)를 만듭니다. 자세한 내용은 참조 [하는 방법: 전용 갤러리에 대 한 Atom 피드 만들기](../extensibility/how-to-create-an-atom-feed-for-a-private-gallery.md)합니다.  
  
-   전용 갤러리를 설명 하는.pkgdef 파일을 배포 합니다. 전용 갤러리를 동시에 여러 컴퓨터에 연결 하려는 관리자에 대 한이 구성을 사용 하는 것이 좋습니다.  
  
## <a name="adding-a-private-gallery-to-extensions-and-updates-in-visual-studio"></a>확장명 및 업데이트 Visual Studio에서 전용 갤러리 추가  
 전용 갤러리를 사용할 수 있는 경우에 추가할 수 있습니다 **확장명 및 업데이트** Visual Studio에서.  
  
 ![확장 관리자 추가 대화 상자](../extensibility/media/em_adddialog.png "EM_AddDialog")  
  
#### <a name="to-add-a-private-gallery-to-extensions-and-updates"></a>확장명 및 업데이트에 전용 갤러리를 추가 하려면  
  
1.  메뉴 모음에서 **도구**, **옵션**을 선택합니다.  
  
2.  에 **환경** 노드를 **확장명 및 업데이트**합니다.  
  
3.  **추가** 단추를 선택합니다.  
  
4.  에 **이름** 필드에, 예를 들어 전용 갤러리에 대 한 이름을 입력 `My Gallery`합니다.  
  
5.  에 **URL** 필드는 Atom 피드 또는 전용 갤러리를 호스팅하는 SharePoint 사이트의 URL을 입력 합니다.  
  
    1.  전용 갤러리에 연결 하는 호스트가 있는 경우 Atom 피드, URL이 중 하나를 유사 하 게: http://www.mywebsite/mygallery/atom.xml 합니다.  이 URL은 파일 또는 네트워크 경로를 참조할 수 있습니다.  
  
    2.  URL이 하나 같습니다 호스트 SharePoint 사이트인 경우: http://mysharepoint/sites/mygallery/forms/AllItems.aspx 합니다.  
  
### <a name="managing-private-galleries"></a>전용 갤러리를 관리합니다.  
 관리자가 사용할 수 전용 갤러리 여러 컴퓨터에 동시에 각 컴퓨터에서 시스템 레지스트리 수정 하 여 합니다. 이를 위해 새 레지스트리 키와 해당 값을 설명 하는.pkgdef 파일을 만듭니다.  이 파일의 형식은 다음과 같습니다.  
  
```  
[$RootKey$\ExtensionManager\Repositories\{UniqueGUID}]  
@={URI}  (REG_SZ)  
Disabled=0 | 1 (DWORD)  
Priority=0 (highest priority) ... MaxInt (lowest priority) (DWORD) (uint)  
Protocol=VSGallery|Atom|Sharepoint (REG_SZ)  
DisplayName={DisplayName} (REG_SZ)  
DisplayNameResourceID={ID} (REG_SZ)  
DisplayNamePackageGuid={GUID} (REG_SZ)  
  
```  
  
 자세한 내용은 참조 [하는 방법: त ा ळ는 개인 갤러리에서 사용 하 여 레지스트리](../extensibility/how-to-manage-a-private-gallery-by-using-registry-settings.md)합니다.  
  
## <a name="installing-extensions-from-a-private-gallery"></a>전용 갤러리에서 확장을 설치합니다.  
 검색 하 고 개인 갤러리에서 Visual Studio 확장을 설치할 수 **확장명 및 업데이트**합니다. 다음 단계에서는 명명 된 전용 갤러리 사용 `My Gallery`합니다.  
  
 ![전용 갤러리를 설치 하는 확장 관리자](../extensibility/media/em_.png "EM_")  
  
#### <a name="to-search-for-and-install-extensions-from-a-private-gallery"></a>검색 하 고 전용 갤러리에서 확장을 설치 합니다.  
  
1.  메뉴 모음에서 **도구**, **확장 및 업데이트**를 선택합니다.  
  
2.  왼쪽된 창에서 선택 **온라인 확장**를 선택한 후 **내 갤러리**합니다.  
  
3.  오른쪽 창에서 확장을 선택한 다음 선택에서 **다운로드** 단추입니다.  
  
## <a name="updating-extensions-from-a-private-gallery"></a>전용 갤러리에서 확장 업데이트  
 새 버전의 Visual Studio 확장 전용 갤러리에 게시 된, 설치 된 확장 업데이트할 수 있습니다. 다음 단계에서는 명명 된 전용 갤러리 사용 `My Repository`합니다.  
  
 ![확장명 관리자 전용 갤러리 업데이트](../extensibility/media/em_update.png "EM_Update")  
  
#### <a name="to-update-an-installed-extension-from-a-private-gallery"></a>전용 갤러리에서 설치 된 확장을 업데이트 하려면  
  
1.  메뉴 모음에서 **도구**, **확장 및 업데이트**를 선택합니다.  
  
2.  왼쪽된 창에서 선택 **업데이트**를 선택한 후 **내 저장소**합니다.  
  
3.  오른쪽 창에서 확장을 선택한 다음 선택에서 **업데이트** 단추입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 확장명 찾기 및 사용](../ide/finding-and-using-visual-studio-extensions.md)   
 [Visual Studio 확장 전달](../extensibility/shipping-visual-studio-extensions.md)
