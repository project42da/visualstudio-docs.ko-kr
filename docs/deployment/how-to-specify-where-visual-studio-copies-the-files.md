---
title: '방법: Visual Studio에서 파일을 복사 하는 위치를 지정 합니다. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publishing, specifying location
- Publish Location property
ms.assetid: 6c552700-dda3-49fe-af98-4717344fda07
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2b4e626253d9d07a9f263304d02739bdb3f4b012
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-specify-where-visual-studio-copies-the-files"></a>방법: Visual Studio의 파일 복사 위치 지정
ClickOnce를 사용하여 응용 프로그램을 게시하는 경우 `Publish Location` 속성에서 응용 프로그램 파일 및 매니페스트가 배치되는 위치를 지정합니다. 이 위치는 파일 경로나 FTP 서버에 대한 경로가 될 수 있습니다.  
  
 지정할 수는 `Publish Location` 속성에는 **게시** 의 페이지는 **프로젝트 디자이너**, 또는 게시 마법사를 사용 하 여 합니다. 자세한 내용은 [하는 방법: 게시 마법사를 사용 하 여 ClickOnce 응용 프로그램을 게시할](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
> [!NOTE]
>  ClickOnce를 사용하여 응용 프로그램 버전을 둘 이상 설치하면 이전 응용 프로그램 버전이 지정한 게시 위치의 Archive 폴더로 이동합니다. 이러한 방식으로 이전 버전이 보관되므로 설치 디렉터리에 이전 버전의 폴더가 남지 않습니다.  
  
### <a name="to-specify-a-publishing-location"></a>게시 위치를 지정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택한 상태에서 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  클릭는 **게시** 탭 합니다.  
  
3.  에 **게시 위치** 필드에, 다음 형식 중 하나를 사용 하 여 게시 위치를 입력 합니다.  
  
    -   파일 공유 나 디스크 경로 게시 하려면 UNC 경로 사용 하 여 경로 입력 (\\\Server\ApplicationName) 또는 파일 경로 (C:\Deploy\ApplicationName).  
  
    -   FTP 서버에 게시하려면 ftp://ftp.microsoft.com/ApplicationName 형식을 사용하여 경로를 입력합니다.  
  
     텍스트에 있어야는 **게시 위치** 찾아보기 위해에서 상자 (**...** ) 단추가 작동 하려면.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)