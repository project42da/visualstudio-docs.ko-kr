---
title: '방법: Atom 만들기 전용 갤러리에 대 한 피드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Atom feed, VSIX private galleries
- VSIX private galleries, Atom feed
ms.assetid: 5897f538-9c41-486f-97d9-a1976d20d9fd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dc39e4d11d826741239f11f62955fa4d2fb167cb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-an-atom-feed-for-a-private-gallery"></a>방법: Atom 만들기 전용 갤러리에 대 한 피드
Atom RSS 피드 확장을 포함 하는 피드를 추가 하는 인트라넷 위치를 만들 수 있습니다 **확장명 및 업데이트** 전용 갤러리로 합니다. 자세한 내용은 [Private Galleries](../extensibility/private-galleries.md)를 참조하세요.  
  
## <a name="creating-an-atom-feed"></a>피드는 Atom 만들기  
 Atom 피드 전용 갤러리로 만들려면 먼저 폴더에 확장 (.vsix 파일)를 수집 합니다. 원하는 경우 하위 폴더에 해당를 구성할 수 있습니다. 또한 다음 리소스를 필요 합니다.  
  
-   확장에서 사용할 수 있도록 전용 갤러리로 atom.xml 파일입니다. Atom.xml 파일을 연결 하는 방법에 대 한 내용은 **확장명 및 업데이트**, 참조 [전용 갤러리](../extensibility/private-galleries.md)합니다.  
  
-   확장 (예를 들어 스크린 샷)에서 추출 된 이미지 파일을 포함 하는 폴더입니다. Atom.xml 파일에서 사용할 수 있도록 이러한 이미지에 대 한 상대 링크 포함 **확장명 및 업데이트**합니다.  
  
 예를 들어 폴더에 다음 두 가지 확장 수집 가정 합니다.  
  
-   Template_Wizard_239.vsix는 빈 VSIX 프로젝트 템플릿입니다.  
  
-   SelectionHighlight.vsix는 선택한 단어의 모든 인스턴스를 강조 표시 하는 도구입니다.  
  
 Atom.xml 파일의 내용을 다음 예제는 다음과 같습니다.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<feed xmlns="http://www.w3.org/2005/Atom">  
<title type="text" />   
<id>uuid:bcecded5-97c8-4d24-96f1-7d9e16652433;id=1</id>   
<updated>2011-04-14T21:25:48Z</updated>   
<entry>  
<id>SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa</id>   
<title type="text">Highlight all occurrences of selected word</title>   
<summary type="text">This extends the editor to highlight ....</summary>   
<published>2011-04-14T14:24:51-07:00</published>   
<updated>2011-04-14T14:24:22-07:00</updated>   
<author>  
<name>Microsoft</name>   
</author>  
<link rel="icon" href="VSIXImages/SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa_Icon_SelectionHighlightIcon.jpg" />   
<link rel="previewimage" href="VSIXImages/SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa_PreviewImage_SelectionHighlight.jpg" />   
<content type="application/octet-stream" src="SelectionHighlight.vsix" />   
<Vsix xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.microsoft.com/developer/vsx-syndication-schema/2010">  
<Id>SelectionHighlight..a14874d2-8199-4a60-af8a-11d6447813aa</Id>   
<Version>1.31</Version>   
<References />   
<Rating xsi:nil="true" />   
<RatingCount xsi:nil="true" />   
<DownloadCount xsi:nil="true" />   
</Vsix>  
</entry>  
<entry>  
<id>Template_Wizard_239.Microsoft.3b38a7e3-5cbc-4389-a92a-d82tyc2ed592</id>   
...  
</entry>  
</feed>
```  
  
 두 링크 태그를 이미지의 생성 된 폴더에 스크린 샷을 참조 하는지 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [전용 갤러리](../extensibility/private-galleries.md)
