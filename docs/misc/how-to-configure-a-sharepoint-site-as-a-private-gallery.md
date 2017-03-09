---
title: "방법: SharePoint 사이트를 전용 갤러리로 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Sharepoint, 전용 갤러리"
  - "전용 갤러리, Sharepoint"
ms.assetid: 6c6ed45f-7e46-4ed0-8b5c-839dbbe3769f
caps.latest.revision: 9
caps.handback.revision: 9
manager: "douge"
---
# 방법: SharePoint 사이트를 전용 갤러리로 구성
확장을 설명하고 전용 갤러리로 제공하는 SharePoint 목록 페이지를 만들고 **확장 및 업데이트**에 목록을 추가할 수 있습니다. 자세한 내용은 [개인 갤러리](../extensibility/private-galleries.md)을 참조하세요.  
  
 SharePoint를 사용하여 전용 갤러리를 만들려면  
  
1.  먼저 전용 갤러리에 대한 목록 페이지를 만듭니다.  
  
2.  그런 다음 확장\(.vsix\) 파일을 목록 페이지의 항목으로 업로드합니다.  
  
> [!IMPORTANT]
>  보안을 위해 SharePoint는 .vsix 파일이 업로드되지 않도록 차단합니다. 전용 갤러리를 설정할 때 .vsix 파일이 차단되지 않도록 합니다. 자세한 내용은 [차단되는 파일 형식 관리](http://go.microsoft.com/fwlink/?LinkID=201253)를 참조하세요.  
  
## 전용 갤러리에 대한 목록 페이지 만들기  
 다음 단계는 배포하는 SharePoint 서버의 구성에 따라 달라질 수 있습니다. 일반적으로 이러한 배포 지침은 SharePoint의 모든 WSP 확장에 대해 동일합니다. SharePoint 솔루션 배포를 관리하는 데 사용할 수 있는 STSAdm 도구에 대한 설명은 MSDN Magazine 웹 사이트에서 [SharePoint 2007을 사용한 솔루션 배포](http://go.microsoft.com/fwlink/?LinkId=220676)를 참조하세요.  
  
#### 전용 갤러리에 대한 목록 페이지를 만들려면  
  
1.  SharePoint 서버에 Visual Studio 확장 목록\(.wsp\) 파일을 업로드합니다.  
  
2.  명령 프롬프트에서 다음 명령을 실행하여 SharePoint 서버에 .wsp 파일을 설치합니다.  
  
     **stsadm –o addsolution –name VisualStudioExtensionsList.wsp**  
  
     **stsadm –o deploysolution –name VisualStudioExtensionsList.wsp –url http:\/\/\<SERVERNAME\> –allowCasPolicies –allowgacdeployment –immediate**  
  
     다음과 같이 하위 사이트에 대한 SharePoint 사용자 인터페이스를 통해 기능을 활성화해야 할 수도 있습니다.  
  
    1.  메뉴 모음에서 **사이트 작업**, **사이트 설정**, **사이트 기능 관리**를 차례로 선택합니다.  
  
    2.  **Visual Studio 확장 라이브러리** 옆에 있는 **활성화** 단추를 선택합니다.  
  
    3.  원하는 하위 사이트에 Visual Studio 확장 라이브러리를 추가합니다.  
  
 목록 페이지를 제거해야 하는 경우 다음 단계를 따르세요.  
  
#### 전용 갤러리에 대한 목록 페이지를 제거하려면  
  
1.  명령 프롬프트에서 다음 명령을 실행하여 SharePoint 서버에서 .wsp 파일을 제거합니다.  
  
     **stsadm –o retractsolution –name VisualStudioExtensionsList.wsp –immediate**  
  
     **stsadm –o deletesolution –name VisualStudioExtensionsList.wsp**  
  
2.  SharePoint에서 솔루션을 취소하고 삭제합니다.  
  
## FAQ  
  
### 확장을 업로드하면 어떻게 되나요?  
 Visual Studio 확장\(.vsix\) 파일을 업로드하면 파일에서 정보가 추출됩니다. 첫 번째로, 포함된 .vsixmanifest 파일에서 일부 값\(예: VsixId, VsixVersion 등\)이 추출되고 해당 SPListItem에 숨겨진 메타데이터 값으로 저장됩니다. 두 번째로, 확장에 대한 아이콘 및 PreviewImage 파일이 추출되고 별도 목록에 저장됩니다.  
  
 이미지는 *ListTitle*\_VSIXIcons 및 *ListTitle*\_VSIXPreviewImages라는 그림 라이브러리에 저장됩니다. 여기서 *ListTitle*은 .vsix 파일을 저장하는 목록 인스턴스의 이름입니다. 모든 이미지 파일의 이름에 해당 VSIX ID가 접두사로 제공됩니다.  
  
### 확장을 삭제하면 어떻게 되나요?  
 .vsix 파일을 삭제하면 해당 이미지 파일\(있는 경우\)도 삭제됩니다.  
  
### 확장을 업데이트하면 어떻게 되나요?  
 .vsix 파일의 새 버전을 업로드하고 기존 버전을 덮어써서 확장을 업데이트할 수 있습니다. 확장을 업데이트하면 확장에 대한 모든 메타데이터 값과 이미지가 새 버전의 값에 따라 업데이트됩니다.  
  
### 목록을 삭제하면 어떻게 되나요?  
 Visual Studio 확장 목록의 인스턴스를 삭제하면 해당 \_VSIXIcons 및 \_VSIXPreviewImages 그림 라이브러리도 삭제됩니다.  
  
### 지원되는 SharePoint 버전은 무엇인가요?  
 현재, SharePoint 2010만 지원됩니다.  
  
## 참고 항목  
 [개인 갤러리](../extensibility/private-galleries.md)